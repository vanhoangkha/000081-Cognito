# Serverless - Authentication with Amazon Cognito

> User authentication with Amazon Cognito.

A hands-on workshop from the [AWS First Cloud Journey](https://github.com/vanhoangkha/aws-first-cloud-journey) series, available in English and Vietnamese.

**Read the workshop online:** https://vanhoangkha.github.io/000081-Cognito/

## Overview

We went through 3 workshops and built a simple web application with the serverless model in the cloud. For our web application to authenticate, the functions are only used when the user is logged in. So in this workshop, we'll learn about AWS Cognito - which provides authentication, authorization, and user management for web and mobile applications.

The architecture of the web application will look like this:

## Workshop contents

1. Preparation
2. Create User Pool
3. Create API and Lambda function
4. Test with front-end
5. Clean up

## Prerequisites

- An AWS account with permissions to create the resources used in the labs
- Basic familiarity with the AWS Management Console
- [Hugo](https://gohugo.io/installation/) (extended edition) if you want to run the site locally

## Run locally

```bash
git clone https://github.com/vanhoangkha/000081-Cognito.git
cd 000081-Cognito
hugo server
```

Then open http://localhost:1313 in your browser.

## Repository structure

| Path | Purpose |
| --- | --- |
| `content/` | Workshop pages (`*.md` English, `*.vi.md` Vietnamese) |
| `static/` | Images and other static assets |
| `layouts/` | Hugo layout overrides |
| `themes/` | Hugo theme |
| `config.toml` | Site configuration |

## Cost and cleanup

The labs create AWS resources that may incur charges. Complete the **Clean up** chapter when you finish to remove them.

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

To report a security issue, see [SECURITY.md](SECURITY.md).

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
