# Other methods

Some of the other methods available, with a small explanation for each:

```text
function WSCreateUsers($params)
```

Creates users in batches. Password is expected unencrypted \(which is alright on HTTPS but **not** otherwise\).

```text
function WSCreateUser($params)
```

Creates just one user.

```text
function WSCreateUsersPasswordCrypted($params)
```

Creates users taking into account their passwords might be encrypted. This method expects the following parameters :

```text
$params = array(
    'secret_key' => $finalKey,
    'users' => array(
        0 => array(
            'firstname' => '…',
            'lastname' => '…',
            'status' => 5,
            'email' => '',
            'loginname' => '',
            'password' => '',
            'encrypt_method' => '',
            'language' => '',
            'phone' => '',
            'expiration_date' => '',
            'official_code' => '',
            'original_user_id_name' => '',
            'original_user_id_value'=> '',
            'extra' => ''
        )
    )
);

function WSCreateUserPasswordCrypted($params)
```

Creates just one user taking into account his password might be encrypted

```text
function WSEditUserCredentials($params)
```

Edits one user's credentials \(username + password\)

```text
function WSEditUsers($params)
```

Edit several users in batch.

```text
function WSEditUser($params)
```

Edit just one user

```text
function WSEditUsersPasswordCrypted($params)
```

Edit users, sending encrypted passwords

```text
function WSEditUserPasswordCrypted($params)
```

Edit one user, sending encrypted password.

**Warning** : although very discrete, there is an issue in Chamilo LMS 1.9.\* whereby WSCreateUserPasswordCrypted expects the username in the form of a « loginname » field, whereas WSEditUserPasswordCrypted expects the username in the form of a « username » field. Make sure you don't fall for this one, as it might be time-costly.

```text
function WSDeleteUsers($params)
```

Delete users in batch

```text
function WSDisableUsers($params)
```

Disable users in batch

```text
function WSEnableUsers($params)
```

Enable users in batch

```text
function WSCreateCourse($params)
```

Create a course

```text
function WSCreateCourseByTitle($params)
```

Create a course giving only a title

```text
function WSEditCourse($params)
```

Edit an existing course

```text
function WSCourseDescription($params)
```

Get the course description for a given course

```text
function WSEditCourseDescription($params)
```

Edit a course description

```text
function WSDeleteCourse($params)
```

Delete a course

```text
function WSCreateSession($params)
```

Create a session. This method expects the following parameters :

```text
$params = array(
    'secret_key' => $finalKey,
    'sessions' => array(
        'name' => '',
        'year_start' => '',
        'month_start' => '',
        'day_start' => '',
        'year_end' => '',
        'month_end' => '',
        'day_end' => '',
        'nb_days_access_before' => '',
        'nb_days_access_after' => '',
        'nolimit' => '',
        //not used in session creation
        'user_id' => '',
        //the coach id
        'original_session_id_name' => '',
        'original_session_id_value'=> '',
        'extra' => ''
    )
);

function WSEditSession($params)
```

Edit one \(or more\) existing session\(s\) based on the original\_session\_id\_value field. This method expects the following parameters :

```text
$params = array(
    'secret_key' => $finalKey,
    'sessions' => array(
        0 => array(
            'name' => '',
            'year_start' => '',
            'month_start' => '',
            'day_start' => '',
            'year_end' => '',
            'month_end' => '',
            'day_end' => '',
            'nb_days_access_before' => '',
            'nb_days_access_after' => '',
            'original_session_id_name' => '',
            'original_session_id_value'=> '',
            'coach_username' => '',
            'nolimit' => '',
            'user_id' => '',
            //the coach id
            'extra' => ''
        ),
    )
);

function WSDeleteSession($params)
```

Delete a session

```text
function WSSubscribeUserToCourse($params)
```

Subscribe a user to a course

```text
function WSSubscribeUserToCourseSimple($params)
```

Subscribe a user to a course

```text
function WSGetUser($params)
```

Get user information from a user ID

```text
function WSGetUserFromUsername($params)
```

Get user information from a username

```text
function WSUnsubscribeUserFromCourse($params)
```

Unsubscribe a user from a course

```text
function WSSuscribeUsersToSession($params)
```

**WARNING : please note the typing mistake here : the service is called « suscribe » instead of « subscribe ». For backwards compatibility, we left it that way, but make no mistake : you have to type it in an incorrect English to make it work !**Subscribe a user to a session. This method expects the following parameters :

```text
$params = array(
    'secret_key' => $finalKey,
    'userssessions' => array(
        0 => array(
            'original_user_id_name' => '',
            'original_user_id_value'=> '',
            'original_session_id_name' => '',
            'original_session_id_value'=> ''
        )
    )
);

function WSSubscribeUserToSessionSimple($params)
```

Unsubscribe a user from a session

```text
function WSUnsuscribeUsersFromSession($params)
```

WARNING : See note in WSSuscribeUsersToSession

Unsubscribe several users from a session in batch

```text
function WSSuscribeCoursesToSession($params)
```

WARNING : See note in WSSuscribeUsersToSession

Subscribe several users to a session in batch. This method expects the following parameters :

```text
$params = array(
    'secret_key' => $finalKey,
    'coursessessions' => array(
        0 => array(
            'original_course_id_name' => '',
            'original_course_id_values' => array(
                0 => array(
                    'course_code' => '',
                    //external course ID (can be int)
                ),
            ),
            'original_session_id_name'=> '',
            'original_session_id_value'=> '',
        )
    )
);

function WSUnsuscribeCoursesFromSession($params)
```

WARNING : See note in WSSuscribeUsersToSession

Remove a course from a session

```text
function WSListCourses($params)
```

Gets a list of courses available on the platform

```text
function WSUpdateUserApiKey($params)
```

Update the API key of a user

```text
function WSListSessions($params)
```

Lists the sessions available on the platform
