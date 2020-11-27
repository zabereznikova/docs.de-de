---
title: Identitätswechsel und Transportsicherheit
ms.date: 03/30/2017
ms.assetid: 426df8cb-6337-4262-b2c0-b96c2edf21a9
ms.openlocfilehash: 14914bc65d5033c54640e06b79713ea1871daf18
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289502"
---
# <a name="using-impersonation-with-transport-security"></a>Identitätswechsel und Transportsicherheit

Identitäts *Wechsel ist die* Fähigkeit einer Serveranwendung, die Identität des Clients zu übernehmen. Dienste greifen bei der Validierung des Zugriffs auf Ressourcen häufig auf den Identitätswechsel zurück. Die Serveranwendung wird unter einem Dienstkonto ausgeführt. Wenn der Server eine Clientverbindung akzeptiert, nimmt er die Identität des Clients an, das heißt, Zugriffsvalidierungen werden mit den Anmeldeinformationen des Clients durchgeführt. Bei der Transportsicherheit handelt es sich um einen Mechanismus, mit dem Anmeldeinformationen übergeben und die Kommunikation mit diesen Anmeldeinformationen gesichert werden können. In diesem Thema wird die Verwendung der Transportsicherheit in Windows Communication Foundation (WCF) mit dem Identitätswechsel Feature beschrieben. Weitere Informationen zum Identitätswechsel mithilfe der Nachrichten Sicherheit finden Sie unter [Delegierung und](delegation-and-impersonation-with-wcf.md)Identitätswechsel.  
  
## <a name="five-impersonation-levels"></a>Die fünf Ebenen des Identitätswechsels  

 Die Transportsicherheit nutzt fünf Ebenen des Identitätswechsels, die in der folgenden Tabelle beschrieben werden.  
  
|Ebene des Identitätswechsels|BESCHREIBUNG|  
|-------------------------|-----------------|  
|Keine|Die Serveranwendung versucht nicht, die Identität des Clients anzunehmen.|  
|Anonym|Die Serveranwendung kann mit den Anmeldeinformationen des Clients Zugriffsüberprüfungen durchführen, erhält jedoch keine Informationen über die Identität des Clients. Diese Ebene des Identitätswechsels ist nur sinnvoll bei einer computerinternen Kommunikation, z.&#160;B. bei Named Pipes (benannten Pipes). Die Verwendung von `Anonymous` mit einer Remoteverbindung erhöht die Ebene des Identitätswechsels auf Identifizieren.|  
|Identify|Die Serveranwendung kennt die Identität des Clients und kann mit den Anmeldeinformationen des Clients Zugriffsvalidierungen durchführen, sie kann jedoch nicht die Identität des Clients annehmen. Identifizierung ist die Standard-Identitätswechsel Ebene, die mit SSPI-Anmelde Informationen in WCF verwendet wird, sofern der Tokenanbieter keine andere Identitätswechsel Ebene bereitstellt.|  
|Impersonate|Die Serveranwendung kann Zugriffsüberprüfungen durchführen und auf dem Servercomputer als Client auf Ressourcen zugreifen. Die Serveranwendung kann jedoch nicht mit der Identität des Clients auf Ressourcen auf Remotecomputern zugreifen, da das Identitätswechsel-Token über keine Anmeldeinformationen für das Netzwerk verfügt.|  
|Delegat|Bei der Identitätswechselebene Delegieren verfügt die Serveranwendung über dieselben Möglichkeiten wie bei der Ebene `Impersonate` und kann zudem unter der Identität des Clients auf Remotecomputer zugreifen und die Identität an andere Anwendungen übergeben.<br /><br /> **Wichtig** Das Server Domänen Konto muss als vertrauenswürdig für die Delegierung auf dem Domänen Controller gekennzeichnet werden, damit diese zusätzlichen Funktionen verwendet werden können. Diese Ebene des Identitätswechsels kann nicht mit als vertraulich eingestuften Clientdomänenkonten verwendet werden.|  
  
 Die bei der Transportsicherheit am häufigsten verwendeten Ebenen sind `Identify` und `Impersonate` . Die Ebenen `None` und `Anonymous` sind nicht für die üblichen Verwendungszwecke zu empfehlen, und bei vielen Transporten werden diese Ebenen nicht für die Authentifizierung unterstützt. Die `Delegate`-Ebene ist eine leistungsstarke Funktion, die nur mit großer Sorgfalt verwendet werden sollte. Nur vertrauenswürdigen Serveranwendungen sollte die Berechtigung gegeben werden, Anmeldeinformationen delegieren zu können.  
  
 Damit der Identitätswechsel mit den Ebenen `Impersonate` oder `Delegate` verwendet werden kann, muss die Serveranwendung die `SeImpersonatePrivilege`-Berechtigung aufweisen. Eine Anwendung verfügt standardmäßig über diese Berechtigung, wenn sie unter einem Konto in der Gruppe der Administratoren oder unter einem Konto mit einer Dienst-SID (Netzwerkdienst, lokaler Dienst oder lokales System) ausgeführt wird. Der Identitätswechsel erfordert keine gegenseitige Authentifizierung von Client und Server. Einige Authentifizierungsschemas, die einen Identitätswechsel unterstützen, wie NTLM, können nicht mit einer gegenseitigen Authentifizierung verwendet werden.  
  
## <a name="transport-specific-issues-with-impersonation"></a>Transportspezifische Aspekte beim Identitätswechsel  

 Die Auswahl eines Transports in WCF wirkt sich auf die möglichen Identitätswechsel Optionen aus. In diesem Abschnitt werden Probleme beschrieben, die die HTTP-und Named Pipe Transporte in WCF betreffen. Benutzerspezifische Transporte haben ihre eigenen Einschränkungen in Bezug auf die Unterstützung eines Identitätswechsels.  
  
### <a name="named-pipe-transport"></a>Named Pipe-Transport  

 Die folgenden Elemente werden mit dem Named Pipe-Transport verwendet:  
  
- Der Named Pipe-Transport ist nur für die Verwendung auf dem lokalen Computer bestimmt. Der Named Pipe-Transport in WCF lässt explizit keine Computer übergreifenden Verbindungen zu.  
  
- Named Pipes können nicht mit den Identitätswechselebenen `Impersonate` und `Delegate` verwendet werden. Die Named Pipe kann bei diesen Identitätswechselebenen keine computerinterne Kommunikation garantieren.  
  
 Weitere Informationen zu Named Pipes finden Sie unter [Auswählen eines Transports](choosing-a-transport.md).  
  
### <a name="http-transport"></a>HTTP-Transport  

 Die Bindungen, die den HTTP-Transport ( <xref:System.ServiceModel.WSHttpBinding> und <xref:System.ServiceModel.BasicHttpBinding> ) verwenden, unterstützen mehrere Authentifizierungs Schemas, wie Untergrund Legendes zur [http-Authentifizierung](understanding-http-authentication.md)erläutert. Die unterstützte Ebene des Identitätswechsels ist abhängig vom Authentifizierungsschema. Die folgenden Elemente werden mit dem HTTP-Transport verwendet:  
  
- Das `Anonymous`-Authentifizierungsschema ignoriert den Identitätswechsel.  
  
- Das `Basic` Authentifizierungsschema unterstützt nur die- `Delegate` Ebene. Alle niedrigeren Identitätswechselebenen werden hochgestuft.  
  
- Das `Digest`-Authentifizierungsschema unterstützt nur die `Impersonate`-Ebene und die `Delegate`-Ebene.  
  
- Das `NTLM`-Authentifizierungsschema, das entweder direkt oder durch Aushandlung ausgewählt werden kann, unterstützt nur die `Delegate`-Ebene auf dem lokalen Computer.  
  
- Das Kerberos-Authentifizierungsschema, das nur durch Aushandlung ausgewählt werden kann, kann mit allen unterstützten Ebenen des Identitätswechsels verwendet werden.  
  
 Weitere Informationen zum HTTP-Transport finden Sie unter [Auswählen eines Transports](choosing-a-transport.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Delegierung und Identitätswechsel](delegation-and-impersonation-with-wcf.md)
- [Autorisierung](authorization-in-wcf.md)
- [Vorgehensweise: Annahme der Clientidentität durch einen Dienst](../how-to-impersonate-a-client-on-a-service.md)
- [Grundlagen der HTTP-Authentifizierung](understanding-http-authentication.md)
