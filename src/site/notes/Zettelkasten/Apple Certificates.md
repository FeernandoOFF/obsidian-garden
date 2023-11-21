---
{"dg-publish":true,"permalink":"/zettelkasten/apple-certificates/","title":"Apple Certificates","tags":["status/todo","core/tech/ios"],"created":"2023-11-13T17:08:28.523+00:00"}
---


# Apple Certificates

> iOS is a **propietary** system and certificates are a way to validate *who* you hare and verify that you have the rights to do it.

The purpose of the certificates is to allow Apple know that you're allowed to do what you're trying to do.

```mermaid
sequenceDiagram

actor Developer
participant Apple
actor iPhone

	Developer-)Apple: Build App
	 Note over Developer,Apple: .Cert file sent
	Apple-)+Developer: Private Key
	Developer-)-Apple: See you later!
```


### Developer Certificates
```mermaid
classDiagram
        Developer *-- Profile
		
        class Developer {
	        Personal Team
	        Developer: + External teams
		}
        class Identifiers {
            define Capabilities
            ? BundleID(com.feernandooff)
        }
        class Certificate {
            -Developer Certificate
            - Districution Certificate
			+download()
        }
        class Profile{
            +bool is_developer
            +bool is ad-hoc
            +bool is development
        }
		Profile <|-- Certificate
		Profile <|-- Identifiers

```



## Relates to
- [[The ‘What’ and ‘Why’ of iOS Signing Certificates and Provisioning Profiles — And How to Manage Them as Your Team Grows\|The ‘What’ and ‘Why’ of iOS Signing Certificates and Provisioning Profiles — And How to Manage Them as Your Team Grows]]
## References
