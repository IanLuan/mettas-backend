# Mettas Backend
The backend for Mettas app.

## Made with
- Node.js
- Express.js
- MongoDB
- Mongoose

## ToDo
 - [X] Create Invite Endpoints
 - [X] Create Endpoint for update user
 - [X] Create Search Endpoints (search metta by full text and user by email)
 - [ ] Add Firebase Admin Auth for google and facebook auth
 - [ ] Create a demo app/web app to consume this API

## API Endpoints

#### Metta Endpoints
| METHOD | ENDPOINT | USAGE | RETURNS |
|:--|:--|:--|:--|
| GET | `/me/mettas` | Get a List of Current User's Mettas | mettas |
| POST | `/me/mettas` | Create a Metta | - |
| GET | `/mettas/{metta_id}` | Get a Metta | metta |
| PUT | `/mettas/{metta_id}` | Change a Metta's Details | - |
| DELETE | `/mettas/{metta_id}` | Remove a Metta | - |
| GET | `/mettas/{metta_id}/transactions` | Get a Metta's Transactions | transactions |
| POST | `/mettas/{metta_id}/transactions` | Add Transaction to a Metta | - |
| GET | `/mettas/{metta_id}/transactions/{transaction_id}` | Get a Transaction | transaction |
| DELETE | `/mettas/{metta_id}/transactions/{transaction_id}` | Remove a Transaction from Metta | - |

#

#### Invite Endpoints (for Metta sharing)
| METHOD | ENDPOINT | USAGE | RETURNS |
|:--|:--|:--|:--|
| GET | `/me/invites` | Get a List of Invites for Current User | invites |
| POST | `/invites/{metta_id}/{guest_id}` | Invite a user to the Metta | - |
| POST | `/invites/{invite_id}` | Accept an Invite | - |
| DELETE | `/invites/{invite_id}` | Reject an Invite | - |

#

#### Auth Endpoints
| METHOD | ENDPOINT | USAGE | RETURNS |
|:--|:--|:--|:--|
| POST | `/signup` | Register a User | token |
| POST | `/signin` | Authenticate a User | token |

#

#### User Endpoints
| METHOD | ENDPOINT | USAGE | RETURNS |
|:--|:--|:--|:--|
| GET | `/me` | Get Current user | user |
| POST | `/me` | Update Current user | - |

#

#### Search Endpoint
| METHOD | ENDPOINT | USAGE | RETURNS |
|:--|:--|:--|:--|
| GET | `/search` | Search users by email or metta by keywords. | user or metta |

| QUERY PARAMETER | TYPE | USAGE | REQUIRED
|:--|:--|:--|:--|
| q | `STRING` | Search query keywords. For example: `q=car`, `q=julia`, `q=ianluan13@gma` | Required |
| type | `STRING` | Item type to search across. Valid types are: `metta`, `user`.  | Required |
