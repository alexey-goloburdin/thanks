erDiagram
    USER ||--|| USER_PROFILE: user_id
    USER ||--|{ USER_AUTHENTICATION: user_id
    USER {
        int id
        boolean is_author
        boolean is_activated
        string email
        string password
    }
    USER_PROFILE {
        int uset_id
        date registration_date
        string first_name
        string last_name
        string phone_number
    }
    USER_AUTHENTICATION {
        int id
        int user_id
        datetime generated_timestamp
        string auth_code
        boolean is_used
    }

    PAYABLE ||--|{ SUBSCRIPTION: payable_id
    PAYABLE {
        int id
        int type
    }
    
    USER ||--|{ SUBSCRIPTION: user_id
    USER }|--|{ USER_SUBSCRIPTIONS: user_id
    SUBSCRIPTION }|--|{ USER_SUBSCRIPTIONS: subscription_id
    PAYABLE ||--|| SUBSCRIPTION: subscription_id
    SUBSCRIPTION {
        int id
        int author_id
        int payable_id
        string name
        text description
        numeric price
    }
    USER_SUBSCRIPTIONS {
        int id
        int user_id
        int subscription_id
        datetime valid_till
    }

    MAILING ||--|{ MAILING_SUBSCRIPTIONS: mailing_id
    SUBSCRIPTION ||--|{ MAILING_SUBSCRIPTIONS: subscription_id
    MAILING {
        int id
        int author_id
        text content
        datetime created_timestamp
        datetime sent_timestamp
    }
    MAILING_SUBSCRIPTIONS {
        int id
        int mailing_id
        int subscription_id
    }


    POST ||--|{ POST_SUBSCRIPTIONS: post_id
    SUBSCRIPTION ||--|{ POST_SUBSCRIPTIONS: subscription_id
    USER ||--|{ POST: author_id
    PAYABLE ||--|| POST: payable_id
    POST ||--|{ POST_LIKES: post_id
    USER ||--|{ POST_LIKES: user_id
    POST {
        int id
        int author_id
        int payable_id
        datetime created_timestamp
        text content
    }
    POST_SUBSCRIPTIONS {
        int id
        int post_id
        int subscription_id
    }
    POST_LIKES {
        int id
        datetime timestamp
        int user_id
        int post_id
    }

    USER ||--|{ DONATION: author_id
    PAYABLE ||--|| DONATION: payable_id
    DONATION {
        int id
        int author_id
        int payable_id
        sting name
        text description
        numeric value_target
    }

    USER ||--|{ TRANSACTION: user_id
    PAYABLE ||--|{ TRANSACTION: payable_id
    TRANSACTION {
        int id
        datetime timestamp
        int user_id
        numeric amount
        int payable_id
    }

Models are not populated with a complete sets of attributes to avoid visual overload

**user** - user instances\
**user_profile** - user's additional information and probably settings\
**user_authentication** - authentications track\
**subscription** - the types of subscriptions an author creates for his subscribers\
**user_subscriptions** - M2M containing each user's subscriptions and their validity\
**mailing** - mailing instances an author creates\
**mailing_subscriptions** - M2M containing types of subscriptions the mailing is sent to\
**post** - author posts\
**post_subscriptions** - M2M containing types of subscriptions the post is visible to\
**post_likes** - post likes track\
**donation** - a dedicated donation initiated by tan author\
**transaction** - payments track\
**payable** - intermediate for payable instances
