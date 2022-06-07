# aws

First, you must create an IAM Role on your AWS account called
``lambda_basic_execution`` with the ``LambdaBasicExecution`` policy attached.

On your computer, create a new virtualenv and project folder.

```bash
$ mkvirtualenv pylambda
(pylambda) $ mkdir pylambda
```

Next, download *Python-Lambda* using pip via pypi.

```bash
(pylambda) $ pip install python-lambda
```

From your ``pylambda`` directory, run the following to bootstrap your project.

```bash
(pylambda) $ lambda init
```

This will create the following files: ``event.json``, ``__init__.py``,
``service.py``, and ``config.yaml``.

Let's begin by opening ``config.yaml`` in the text editor of your choice. For
the purpose of this tutorial, the only required information is
``aws_access_key_id`` and ``aws_secret_access_key``. You can find these by
logging into the AWS management console.

Next let's open ``service.py``, in here you'll find the following function:

```python
def handler(event, context):
    # Your code goes here!
    e = event.get('e')
    pi = event.get('pi')
    return e + pi
```

This is the handler function; this is the function AWS Lambda will invoke in
response to an event. You will notice that in the sample code ``e`` and ``pi``
are values in a ``dict``. AWS Lambda uses the ``event`` parameter to pass in
event data to the handler.
