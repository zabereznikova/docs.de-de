---
title: Anspruchsbasiertes Identitätsmodell
ms.date: 03/30/2017
ms.assetid: 4a96a9af-d980-43be-bf91-341a23401431
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: dadcc397783e003574d417aa6253ebc561ed28db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398894"
---
# <a name="claims-based-identity-model"></a>Anspruchsbasiertes Identitätsmodell
Wenn Sie Ansprüche unterstützende Anwendungen erstellen, wird die Benutzeridentität in der Anwendung als Satz von Ansprüchen dargestellt. Ein Anspruch ist möglicherweise der Name des Benutzers, ein anderer eine e-Mail-Adresse. Das zugrunde liegende Konzept besteht darin, dass ein externes Identitätssystem konfiguriert wird, um der Anwendung mit jeder Anforderung alle erforderlichen Informationen über den Benutzer zu geben. Außerdem wird die kryptografische Zusicherung gegeben, dass die Identitätsdaten, die Sie erhalten, aus einer vertrauenswürdigen Quelle stammen.  
  
 Bei diesem Modell ist das einmalige Anmelden viel einfacher zu erreichen, und die Anwendung ist nicht mehr für Folgendes zuständig:  
  
-   Authentifizieren von Benutzern.  
  
-   Speichern von Benutzerkonten und Kennwörtern.  
  
-   Aufrufen der Unternehmensverzeichnisse, um Benutzeridentitätsdetails zu suchen.  
  
-   Integration in Identitätssysteme anderer Plattformen oder Unternehmen.  
  
 Bei diesem Modell trifft die Anwendung identitätsbezogene Entscheidungen auf der Grundlage von Ansprüchen, die von dem System bereitgestellt werden, das den Benutzer authentifizierte. Dabei kann es sich um die einfache Anwendungspersonalisierung mit dem Vornamen des Benutzers oder um das Autorisieren des Benutzers für den Zugriff auf höherwertige Funktionen und Ressourcen in der Anwendung handeln.  
  
 Dieses Thema enthält folgende Informationen:  
  
-   [Einführung in die anspruchsbasierte Identität](../../../docs/framework/security/claims-based-identity-model.md#BKMK_1)  
  
-   [Grundlegendes Szenario für ein anspruchsbasiertes Identitätsmodell](../../../docs/framework/security/claims-based-identity-model.md#BKMK_2)  
  
<a name="BKMK_1"></a>   
## <a name="introduction-to-claims-based-identity"></a>Einführung in die anspruchsbasierte Identität  
 Die folgende Terminologie und Konzepte können Ihnen helfen, diese neue Architektur zur Identifizierung zu verstehen.  
  
### <a name="identity"></a>Identität  
 Für die Beschreibung des Programmiermodells in Windows Identity Foundation (WIF) verwenden wir den Begriff „Identität“ um einen Satz von Attributen darzustellen, die einen Benutzer oder eine andere Entität in einem System beschreiben, das Sie sicher machen möchten.  
  
### <a name="claim"></a>Anspruch  
 Stellen Sie sich einen Anspruch als eine bestimmte Identitätsinformation wie Name, e-Mail-Adresse, Alter, Mitgliedschaft in der Rolle "Sales". Je mehr Ansprüche die Anwendung empfängt, desto mehr wissen Sie über den Benutzer. Sie fragen sich vielleicht, warum diese als „Ansprüche“ bezeichnet werden und nicht als „Attribute“, wie es häufig beim Beschreiben von Unternehmensverzeichnissen verwendet wird. Dies liegt in der Übermittlungsmethode begründet. In diesem Modell sucht die Anwendung nicht nach Benutzerattributen in einem Verzeichnis. Stattdessen stellt der Benutzer Ansprüche an die Anwendung, die von der Anwendung überprüft werden. Jeder Anspruch wird von einem Aussteller gestellt, und Sie vertrauen dem Anspruch nur so weit, wie Sie dem Aussteller vertrauen. Beispielsweise vertrauen Sie einem Anspruch, der vom Domänencontroller Ihres Unternehmens gestellt wurde, mehr als einem Anspruch vom Benutzer selbst. WIF stellt Ansprüche mit einem <xref:System.Security.Claims.Claim>-Typ dar, der über eine <xref:System.Security.Claims.Claim.Issuer%2A>-Eigenschaft verfügt, mit der Sie feststellen können, wer den Anspruch ausgegeben hat.  
  
### <a name="security-token"></a>Sicherheitstoken  
 Der Benutzer stellt der Anwendung einen Satz von Ansprüchen zusammen mit einer Anforderung bereit. In einem Webdienst werden diese Ansprüche im Sicherheitsheader des SOAP-Umschlags transportiert. In einer browserbasierten Webanwendung werden die Ansprüche möglicherweise über ein HTTP POST vom Browser des Benutzers empfangen und später in einem Cookie zwischengespeichert, wenn eine Sitzung gewünscht wird. Unabhängig davon, wie diese Ansprüche empfangen werden, müssen sie serialisiert werden. An dieser Stelle kommen die Sicherheitstoken ins Spiel. Ein Sicherheitstoken ist ein Satz von serialisierten Ansprüchen, der durch die ausstellende Stelle digital signiert ist. Die Signatur ist wichtig: Sie verleiht Ihnen die Sicherheit, dass der Benutzer nicht einen beliebigen Satz von Ansprüchen zusammengestellt und an Sie gesendet hat. In Situationen mit niedrigen Sicherheitsanforderungen, in denen Kryptografie nicht notwendig oder gewünscht ist, können Sie nicht signierte Token verwenden. Dieses Szenario wird jedoch in diesem Thema nicht beschrieben.  
  
 Eine der wichtigsten Funktionen in WIF ist die Fähigkeit, Sicherheitstoken zu erstellen und zu lesen. WIF und .NET Framework erledigen alle kryptografischen Aufgaben und legen der Anwendung einen Satz von Ansprüchen vor, den Sie lesen können.  
  
### <a name="issuing-authority"></a>Ausstellende Stelle  
 Es gibt viele verschiedene Arten von ausstellenden Stellen, angefangen von Domänencontrollern, die Kerberos-Tickets ausgeben, bis zu Zertifizierungsstellen, die X.509-Zertifikate ausstellen. In diesem Thema geht es jedoch um ausstellende Stellen für Sicherheitstoken, welche Ansprüche enthalten. Bei einer solchen ausstellenden Stelle handelt es sich um eine Webanwendung oder einen Webdienst, die bzw. der Sicherheitstoken ausgeben kann. Die Anwendung bzw. der Dienst muss über genügend Informationen verfügen, um die für die vertrauende Zielseite und den die Anforderung stellenden Benutzer richtigen Ansprüche auszugeben. Die Anwendung bzw. der Dienst kann für die Interaktion mit Benutzerspeichern zuständig sein, um Ansprüche zu suchen und die Benutzer zu authentifizieren.  
  
 Welche ausstellende Stelle Sie auch wählen – sie spielt eine zentrale Rolle in der Identitätslösung. Wenn Sie die Authentifizierung aus der Anwendung verlagern und auf Ansprüche vertrauen, übertragen Sie die Verantwortung auf die ausstellende Stelle und fordern sie auf, die Benutzer für Sie zu authentifizieren.  
  
### <a name="security-token-service-sts"></a>Sicherheitstokendienst (STS; Security Token Service)  
 Ein Sicherheitstokendienst (STS) ist die Dienstkomponente, die Sicherheitstoken entsprechend den WS-Trust- und WS-Verbund-Protokollen erstellt, signiert und ausgibt. Das Implementieren dieser Protokolle erfordert einigen Aufwand, doch diese Aufgabe erledigt WIF für Sie. So können Sie einen STS mit relativ geringem Aufwand installieren und ausführen, ohne sich mit den Protokollen auskennen zu müssen. Sie können einen vordefinierten STS wie [Active Directory®-Verbunddienste (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) oder einen Cloud-STS wie [Microsoft Azure-Zugriffssteuerungsdienst (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) verwenden. Sie können auch einen benutzerdefinierten STS mit WIF erstellen, wenn Sie benutzerdefinierte Token ausgeben oder eine benutzerdefinierte Authentifizierung oder Autorisierung bereitstellen möchten. Mit WIF können Sie einen eigenen STS einfach erstellen.  
  
### <a name="relying-party-application"></a>Anwendung der vertrauenden Seite  
 Wenn Sie eine Anwendung erstellen, die auf Ansprüche basiert ist, erstellen Sie eine Anwendung der vertrauenden Seite. Synonyme für eine Anwendung der vertrauenden Seite sind „Ansprüche unterstützende Anwendung“ und „anspruchsbasierte Anwendung“. Webanwendungen und Webdienste können Anwendungen der vertrauenden Seite sein. Eine Anwendung der vertrauenden Seite nutzt die Token, die von einem STS ausgegeben werden, und extrahiert die Ansprüche der Token, um sie für identitätsbezogene Aufgaben zu verwenden. WIF bietet Funktionen, die Sie beim Erstellen von Anwendungen der vertrauenden Seite unterstützen.  
  
### <a name="standards"></a>Standards  
 Aus Gründen der Interoperabilität werden im vorherigen Szenario einige WS-*Standards verwendet. Die Richtlinie wird mithilfe von WS-MetadataExchange abgerufen, und die Richtlinie selbst wird entsprechend der WS-Policy-Spezifikation strukturiert. Der STS macht Endpunkte verfügbar, mit denen die WS-Trust-Spezifikation implementiert wird. Diese beschreibt, wie Sicherheitstoken angefordert und abgerufen werden. Die meisten modernen STS-Dienste geben Token aus, die mit Security Assertion Markup Language (SAML) formatiert werden. SAML ist ein in der Branche anerkanntes XML-Vokabular, das verwendet werden kann, um Ansprüche interoperabel darzustellen. Wenn Sie über mehrere Plattformen verfügen, können Sie mithilfe von SAML mit einem STS auf einer anderen Plattform kommunizieren und einmaliges Anmelden für alle Anwendungen, unabhängig von der jeweiligen Plattform, implementieren.  
  
### <a name="browser-based-applications"></a>Browserbasierte Anwendungen  
 Das anspruchsbasierte Identitätsmodell wird nicht nur von intelligenten Clients verwendet. Das Modell ist auch bei browserbasierten Anwendungen (auch als passive Clients bezeichnet) einsetzbar. Im folgenden Szenario wird beschrieben, wie dies funktioniert.  
  
 Zunächst verweist der Benutzer einen Browser auf eine Ansprüche unterstützende Webanwendung (die Anwendung der vertrauenden Seite). Die Webanwendung leitet den Browser an den STS um, sodass der Benutzer authentifiziert werden kann. Der STS wird in einer einfachen Webanwendung gehostet, die die eingehende Anforderung liest, den Benutzer mithilfe von HTTP-Standardmechanismen authentifiziert und dann ein SAML-Token erstellt. Der Dienst antwortet mit einem JavaScript-Code, der den Browser veranlasst, HTTP POST zu initiieren, der das SAML-Token wieder an die Anwendung der vertrauenden Seite sendet. Der Text der POST-Anforderung enthält die Ansprüche, die die Anwendung der vertrauenden Seite anforderte. Von der Anwendung der vertrauenden Seite werden die Ansprüche üblicherweise in einem Cookie gespeichert, sodass der Benutzer nicht für jede Anforderung umgeleitet werden muss.  
  
<a name="BKMK_2"></a>   
## <a name="basic-scenario-for-a-claims-based-identity-model"></a>Grundlegendes Szenario für ein anspruchsbasiertes Identitätsmodell  
 Hier ein Beispiel für ein anspruchsbasiertes System.  
  
 ![Authentifizierungsfluss des abhängigen Partners](../../../docs/framework/security/media/conc-relying-partner-processc.png "Conc_relying_partner_processc")  
  
 Dieses Diagramm zeigt eine Website (die Anwendung der vertrauenden Seite), die konfiguriert wurde, um WIF zur Authentifizierung zu verwenden, und einen Client, in diesem Fall einen Webbrowser, der diese Website verwenden möchte.  
  
1.  Wenn ein nicht authentifizierter Benutzer eine Seite anfordert, wird der Browser an die Seiten des Identitätsanbieters (IP) umgeleitet.  
  
2.  Der IP fordert den Benutzer auf, seine Anmeldeinformationen, z. B. Benutzername/Kennwort, Kerberos, anzugeben.  
  
3.  Der IP gibt ein Token aus, das an den Browser zurückgegeben wird.  
  
4.  Der Browser wird jetzt wieder an die ursprünglich angeforderte Seite umgeleitet, wo WIF bestimmt, ob das Token die Anforderungen erfüllt und auf die Seite zugreifen darf. Falls ja, wird ein Cookie ausgegeben, um eine Sitzung zu starten. Die Authentifizierung muss daher nur einmal erfolgen und die Kontrolle wird an die Anwendung übergeben.
