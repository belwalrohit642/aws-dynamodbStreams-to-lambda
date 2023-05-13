**AWS dynamoDB Streams to lambda**
This code is a Python implementation of an AWS Lambda function that listens for DynamoDB stream events and processes them based on their event type (INSERT, MODIFY, or REMOVE).

The lambda_handler function is the main entry point for the Lambda function. It receives the event parameter, which is a dictionary containing information about the DynamoDB stream event, and the context parameter, which is a dictionary containing information about the Lambda execution environment.

The handle_insert, handle_modify, and handle_remove functions are event handlers that are called depending on the type of the event received. They parse the information from the event and perform actions based on the event type.

The handle_insert function prints a message indicating that a new row was added to the DynamoDB table, along with the ID of the new player.

The handle_modify function prints a message indicating that a score has changed if the score value of the modified record has changed.

The handle_remove function prints a message indicating that a row has been removed from the DynamoDB table, along with the ID of the player that was removed.

The lambda_handler function iterates over each record in the event dictionary and calls the appropriate event handler based on the eventName field of the record. If an exception occurs during execution, the function prints the exception and returns an error message. If no exception occurs, the function returns a success message.