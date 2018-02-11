Create Account
=============

Query:
```
mutation CreateAccount($account: CreateAccountInput!) {
  createAccount(input: $account) {
    changedAccount {
      id
      name
    }
  }
}
```
Variables:
```
{
  "account": {
    "name": "TestAccountCreation"
  }
}
```

Create User
=========== 

Query:
```
mutation createUser($user: CreateUserInput!) {
  createUser(input: $user) {
    changedUser {
      id
      username
      email
    }
  }
}
```
Variables:
```
{
  "user": {
    "accountId": "QWNjb3VudDoz",
    "username": "abcdarium",
    "password": "123456",
    "email": "test@test.de"
  }
}
```
Login
=========

Query:
```
mutation LoginUserQuery ($input: LoginUserInput!) {
	loginUser(input: $input) {
		token
		user {
			id
			username
			createdAt
		}
    }
}
```
Variables:
```
{
	"input": {
		"username": "akrivonos-test",
		"password": "123456"
	}
}
```

Get Board
=========
```
{
	getBoard(id: "Qm9hcmQ6MQ==") {
		name
		createdAt
		card_board(
			first: 5
		) {
			edges {
				cursor
				node {
					content
					parent {
						id
					}
				}
			}
		}
	}
}
```

Create card
===========

Query:
```
mutation CreateCard($card: CreateCardInput!) {
  createCard(input: $card) {
    changedCard {
      id
      content
    }
  }
}
```
Variables:
```
{
  "card": {
    "parent": null,
    "isExpanded": false,
    "boardId": "Qm9hcmQ6MQ==",
    "authorId": "VXNlcjo3",
    "accountId": "QWNjb3VudDoy",
    "content": "lotem ipsum test create"
  }
}
```
