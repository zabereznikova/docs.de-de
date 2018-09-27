---
title: Identitätswechsel und Transportsicherheit
ms.date: 03/30/2017
ms.assetid: 426df8cb-6337-4262-b2c0-b96c2edf21a9
author: BrucePerlerMS
ms.openlocfilehash: 537bb1d9cfbda98b0e92833d94b40097fae205fd
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397032"
---
# <a name="using-impersonation-with-transport-security"></a>Identitätswechsel und Transportsicherheit
*Identitätswechsel* ist die Fähigkeit einer Serveranwendung, die Identität des Clients anzunehmen. Dienste greifen bei der Validierung des Zugriffs auf Ressourcen häufig auf den Identitätswechsel zurück. Die Serveranwendung wird unter einem Dienstkonto ausgeführt. Wenn der Server eine Clientverbindung akzeptiert, nimmt er die Identität des Clients an, das heißt, Zugriffsvalidierungen werden mit den Anmeldeinformationen des Clients durchgeführt. Bei der Transportsicherheit handelt es sich um einen Mechanismus, mit dem Anmeldeinformationen übergeben und die Kommunikation mit diesen Anmeldeinformationen gesichert werden können. Dieses Thema beschreibt, mit der Identitätswechselfunktion Transport Security in Windows Communication Foundation (WCF) verwenden. Weitere Informationen zum Identitätswechsel unter Verwendung der nachrichtensicherheit finden Sie unter [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="five-impersonation-levels"></a>Die fünf Ebenen des Identitätswechsels  
 Die Transportsicherheit nutzt fünf Ebenen des Identitätswechsels, die in der folgenden Tabelle beschrieben werden.  
  
|Ebene des Identitätswechsels|Beschreibung|  
|-------------------------|-----------------|  
|Keiner|Die Serveranwendung versucht nicht, die Identität des Clients anzunehmen.|  
|Anonym|Die Serveranwendung kann mit den Anmeldeinformationen des Clients Zugriffsüberprüfungen durchführen, erhält jedoch keine Informationen über die Identität des Clients. Diese Ebene des Identitätswechsels ist nur sinnvoll bei einer computerinternen Kommunikation, z.&#160;B. bei Named Pipes (benannten Pipes). Die Verwendung von `Anonymous` mit einer Remoteverbindung erhöht die Ebene des Identitätswechsels auf Identifizieren.|  
|Identifizieren (Identify)|Die Serveranwendung kennt die Identität des Clients und kann mit den Anmeldeinformationen des Clients Zugriffsvalidierungen durchführen, sie kann jedoch nicht die Identität des Clients annehmen. Identifizieren ist die Standard-Identitätswechselebene, die mit SSPI-Anmeldeinformationen in WCF verwendet werden, es sei denn, der Sicherheitstoken-Anbieter eine andere Identitätswechselebene enthält.|  
|Identitätswechsel|Die Serveranwendung kann Zugriffsüberprüfungen durchführen und auf dem Servercomputer als Client auf Ressourcen zugreifen. Die Serveranwendung kann jedoch nicht mit der Identität des Clients auf Ressourcen auf Remotecomputern zugreifen, da das Identitätswechsel-Token über keine Anmeldeinformationen für das Netzwerk verfügt.|  
|delegate|Bei der Identitätswechselebene Delegieren verfügt die Serveranwendung über dieselben Möglichkeiten wie bei der Ebene `Impersonate` und kann zudem unter der Identität des Clients auf Remotecomputer zugreifen und die Identität an andere Anwendungen übergeben.<br /><br /> **Wichtige** das Domänenkonto für die Server muss markiert werden als vertrauenswürdig für die Delegierung auf dem Domänencontroller, um diese zusätzlichen Funktionen verwenden. Diese Ebene des Identitätswechsels kann nicht mit als vertraulich eingestuften Clientdomänenkonten verwendet werden.|  
  
 Die mit der transportsicherheit am häufigsten verwendeten Ebenen sind `Identify` und `Impersonate`. Die Ebenen `None` und `Anonymous` sind nicht für die üblichen Verwendungszwecke zu empfehlen, und bei vielen Transporten werden diese Ebenen nicht für die Authentifizierung unterstützt. Die `Delegate`-Ebene ist eine leistungsstarke Funktion, die nur mit großer Sorgfalt verwendet werden sollte. Nur vertrauenswürdigen Serveranwendungen sollte die Berechtigung gegeben werden, Anmeldeinformationen delegieren zu können.  
  
 Damit der Identitätswechsel mit den Ebenen `Impersonate` oder `Delegate` verwendet werden kann, muss die Serveranwendung die `SeImpersonatePrivilege`-Berechtigung aufweisen. Eine Anwendung verfügt standardmäßig über diese Berechtigung, wenn sie unter einem Konto in der Gruppe der Administratoren oder unter einem Konto mit einer Dienst-SID (Netzwerkdienst, lokaler Dienst oder lokales System) ausgeführt wird. Der Identitätswechsel erfordert keine gegenseitige Authentifizierung von Client und Server. Einige Authentifizierungsschemas, die einen Identitätswechsel unterstützen, wie NTLM, können nicht mit einer gegenseitigen Authentifizierung verwendet werden.  
  
## <a name="transport-specific-issues-with-impersonation"></a>Transportspezifische Aspekte beim Identitätswechsel  
 Die Auswahl eines Transports in WCF wirkt sich auf die möglichen Optionen für den Identitätswechsel. Dieser Abschnitt beschreibt Probleme, die Auswirkungen auf die standard-HTTP und named Pipe-Transporte in WCF. Benutzerspezifische Transporte haben ihre eigenen Einschränkungen in Bezug auf die Unterstützung eines Identitätswechsels.  
  
### <a name="named-pipe-transport"></a>Named Pipe-Transport  
 Die folgenden Elemente werden mit dem Named Pipe-Transport verwendet:  
  
-   Der Named Pipe-Transport ist nur für die Verwendung auf dem lokalen Computer bestimmt. Die named Pipe-Transport in WCF lässt explizit keine computerübergreifenden Verbindungen zu.  
  
-   Named Pipes können nicht mit den Identitätswechselebenen `Impersonate` und `Delegate` verwendet werden. Die Named Pipe kann bei diesen Identitätswechselebenen keine computerinterne Kommunikation garantieren.  
  
 Weitere Informationen zu named Pipes finden Sie unter [Wählen eines Transports](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).  
  
### <a name="http-transport"></a>HTTP-Transport  
 Die Bindungen, die den HTTP-Transport verwenden (<xref:System.ServiceModel.WSHttpBinding> und <xref:System.ServiceModel.BasicHttpBinding>) unterstützen verschiedene Authentifizierungsschemas, siehe [Understanding HTTP Authentication](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md). Die unterstützte Ebene des Identitätswechsels ist abhängig vom Authentifizierungsschema. Die folgenden Elemente werden mit dem HTTP-Transport verwendet:  
  
-   Das `Anonymous`-Authentifizierungsschema ignoriert den Identitätswechsel.  
  
-   Die `Basic` -Authentifizierungsschema unterstützt nur die `Delegate` Ebene. Alle niedrigeren Identitätswechselebenen werden hochgestuft.  
  
-   Das `Digest`-Authentifizierungsschema unterstützt nur die `Impersonate`-Ebene und die `Delegate`-Ebene.  
  
-   Das `NTLM`-Authentifizierungsschema, das entweder direkt oder durch Aushandlung ausgewählt werden kann, unterstützt nur die `Delegate`-Ebene auf dem lokalen Computer.  
  
-   Das Kerberos-Authentifizierungsschema, das nur durch Aushandlung ausgewählt werden kann, kann mit allen unterstützten Ebenen des Identitätswechsels verwendet werden.  
  
 Weitere Informationen zu den HTTP-Transport, finden Sie unter [Wählen eines Transports](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Delegierung und Identitätswechsel](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [Vorgehensweise: Annahme der Clientidentität durch einen Dienst](../../../../docs/framework/wcf/how-to-impersonate-a-client-on-a-service.md)  
 [Grundlagen der HTTP-Authentifizierung](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)
