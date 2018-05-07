---
title: Anspruchsbasierte Autorisierung mit WIF
ms.date: 03/30/2017
ms.assetid: e24000a3-8fd8-4c0e-bdf0-39882cc0f6d8
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 1d2972ccef6829a2b7a052ba30258086443bd833
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="claims-based-authorization-using-wif"></a>Anspruchsbasierte Autorisierung mit WIF
In einer Anwendung der vertrauenden Seite bestimmt die Autorisierung, auf welche Ressourcen eine authentifizierte Identität zugreifen und welche Vorgänge sie mit diesen Ressourcen ausführen darf. Eine falsche oder schwache Autorisierung führt zu Offenlegung von Informationen und Datenmanipulation. In diesem Thema werden die verfügbaren Methoden zum Implementieren der Autorisierung für Ansprüche unterstützende ASP.NET-Webanwendungen und -Dienste mit Windows Identity Foundation (WIF) und einem Sicherheitstokendienst (STS) wie Microsoft Azure-Zugriffssteuerungsdienst (ACS) beschrieben.  
  
## <a name="overview"></a>Übersicht  
 Seit der ersten Version bietet .NET Framework einen flexiblen Mechanismus zum Implementieren der Autorisierung. Dieser Mechanismus basiert auf zwei einfachen Schnittstellen: **IPrincipal** und **IIdentity**. Konkrete Implementierungen von **IIdentity** stellen einen authentifizierten Benutzer dar. Beispielsweise stellt die **WindowsIdentity**-Implementierung einen Benutzer dar, der durch Active Directory authentifiziert wird, und **GenericIdentity** stellt einen Benutzer dar, dessen Identität über einen benutzerdefinierten Authentifizierungsprozess bestätigt wird. Konkrete Implementierungen von **IPrincipal** helfen bei der Überprüfung von Berechtigungen mithilfe von Rollen je nach Rollenspeicher. Beispielsweise überprüft **WindowsPrincipal** **WindowsIdentity** auf die Mitgliedschaft in den Active Directory-Gruppen. Diese Überprüfung wird ausgeführt, indem die **IsInRole**-Methode in der **IPrincipal**-Schnittstelle aufgerufen wird. Die Überprüfung des Zugriffs anhand von Rollen wird als rollenbasierte Zugriffssteuerung (RBAC) bezeichnet. Weitere Informationen finden Sie unter [Rollenbasierte Zugriffssteuerung](../../../docs/framework/security/claims-based-authorization-using-wif.md#BKMK_1).  Ansprüche können verwendet werden, um Informationen über Rollen weiterzugeben und so die vertrauenswürdigen, rollenbasierten Autorisierungsmechanismen zu unterstützen.  
  
 Ansprüche können auch verwendet werden, um komplexere Autorisierungsentscheidungen über Rollen hinaus zu ermöglichen. Ansprüche können auf nahezu allen Informationen über den Benutzer – Alter, Postleitzahl, Schuhgröße usw. – basieren. Ein Mechanismus zur Zugriffskontrolle, der auf beliebigen Ansprüchen basiert, wird anspruchsbasierte Autorisierung genannt. Weitere Informationen finden Sie unter [Anspruchsbasierte Autorisierung](../../../docs/framework/security/claims-based-authorization-using-wif.md#BKMK_2).  
  
<a name="BKMK_1"></a>   
## <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung  
 RBAC ist ein Autorisierungsansatz, in dem eine Anwendung Benutzerberechtigungen anhand von Benutzerrollen verwaltet und erzwingt. Wenn ein Benutzer über eine Rolle verfügt, die zum Ausführen einer Aktion erforderlich ist, wird der Zugriff erteilt. Andernfalls wird der Zugriff verweigert.  
  
### <a name="iprincipalisinrole-method"></a>IPrincipal.IsInRole-Methode  
 Um den RBAC-Ansatz in Ansprüche unterstützende Anwendungen zu implementieren, verwenden Sie die **IsInRole()**-Methode in der **IPrinicpal**-Schnittstelle auf die gleiche Weise wie für Anwendungen, die keine Ansprüche unterstützen. Es gibt mehrere Möglichkeiten für den Einsatz der **IsInRole()**-Methode:  
  
-   Explizites Aufrufen von **IPrincipal.IsInRole("Administrator")**. Das Ergebnis dieser Methode ist ein boolescher Wert. Verwenden Sie diese Methode in Bedingungsanweisungen. Sie kann an einer beliebigen Stelle im Code verwendet werden.  
  
-   Verwenden der Sicherheitsforderung **PrincipalPermission.Demand()**. In diesem Ansatz ist das Ergebnis eine Ausnahme, falls die Anforderung nicht erfüllt wird. Der Ansatz sollte zu Ihrer Ausnahmebehandlungsstrategie passen. Das Auslösen von Ausnahmen ist bezogen auf die Leistung im Vergleich zur Deaktivierung des booleschen Werts wesentlich nachteiliger. Dieser Ansatz kann an jeder beliebigen Stelle im Code verwendet werden.  
  
-   Verwenden deklarativer Attribute **[PrincipalPermission(SecurityAction.Demand, Role = "Administrator")]**. Dieser Ansatz wird als deklarativ bezeichnet, da er verwendet wird, um Methoden zu ergänzen. Er kann nicht in den Codeblöcken innerhalb der Implementierungen der Methode verwendet werden. Das Ergebnis ist eine Ausnahme, falls die Anforderung nicht erfüllt wird. Sie sollten überprüfen, ob dieser Ansatz Ihrer Ausnahmebehandlungsstrategie entspricht.  
  
-   Verwenden der URL-Autorisierung mithilfe des **\<Autorisierung>**-Abschnitts in **web.config**. Dieser Ansatz ist geeignet, wenn Sie die Autorisierung auf URL-Ebene verwalten. Dies ist von allen bisher erwähnten Ebenen die gröbste Ebene. Der Vorteil dieser Methode ist, dass Änderungen in der Konfigurationsdatei vorgenommen werden, d. h., dass der Code nicht kompiliert werden sollte, um von der Änderung zu profitieren.  
  
### <a name="expressing-roles-as-claims"></a>Ausdrücken von Rollen als Ansprüche  
 Wenn die **IsInRole()**-Methode aufgerufen wird, wird eine Prüfung durchgeführt, um festzustellen, ob der aktuelle Benutzer diese Rolle besitzt. In den Ansprüche unterstützenden Anwendungen wird die Rolle durch einen Rollenanspruchstyp ausgedrückt, der im Token verfügbar sein soll. Der Rollenanspruchstyp wird mithilfe des folgenden URI ausgedrückt:  
  
 http://schemas.microsoft.com/ws/2008/06/identity/claims/role  
  
 Es gibt mehrere Möglichkeiten, ein Token mit einem Rollenanspruchstyp zu erweitern:  
  
-   **Während der Tokenausstellung**. Wenn ein Benutzer authentifiziert wird, kann der Rollenanspruch vom Identitätsanbieter-STS oder von einem Verbundanbieter wie dem Microsoft Azure-Zugriffssteuerungsdienst (ACS) ausgegeben werden.  
  
-   **Transformieren beliebiger Ansprüche mit ClaimsAuthenticationManager in einen Anspruchsrollentyp**. ClaimsAuthenticationManager ist eine Komponente, die im Lieferumfang von WIF enthalten ist. Sie ermöglicht ein Abfangen von Anforderungen, wenn diese eine Anwendung starten. Dabei werden Token überprüft und transformiert, indem Ansprüche hinzugefügt, geändert oder entfernt werden. Weitere Informationen zum Verwenden von ClaimsAuthenticationManager zum Transformieren von Ansprüchen finden Sie unter [Vorgehensweise: Implementieren Rolle rollenbasierten Zugriffssteuerung (RBAC) in einem Ansprüche beachten ASP.NET Anwendung mithilfe von WIF und ACS](http://go.microsoft.com/fwlink/?LinkID=247445) (http://go.microsoft.com/fwlink/?LinkID=247444).  
  
-   **Zuordnen von beliebigen Ansprüchen zu einem Rollentyp mithilfe des samlSecurityTokenRequirement-Konfigurationsabschnitts**. Dies ist ein deklarativer Ansatz, bei dem die Anspruchstransformation nur mithilfe der Konfiguration durchgeführt wird. Eine Codierung ist nicht erforderlich.  
  
<a name="BKMK_2"></a>   
## <a name="claims-based-authorization"></a>Anspruchsbasierte Autorisierung  
 Die anspruchsbasierte Autorisierung ist ein Ansatz, bei dem die Autorisierungsentscheidung, den Zugriff zu gewähren oder zu verweigern, auf beliebiger Logik basiert. Diese Logik trifft die Entscheidung mithilfe der in Ansprüchen verfügbaren Informationen. Beachten Sie, dass der einzige Anspruch, der in RBAC verwendet wird, der Rollentyp ist. Ein Rollentypanspruch wurde verwendet, um zu überprüfen, ob der Benutzer zu einer bestimmten Rolle gehört oder nicht. Die folgenden Schritte veranschaulichen den Prozess zum Treffen der Autorisierungsentscheidungen mithilfe des anspruchsbasierten Autorisierungsansatzes:  
  
1.  Die Anwendung empfängt eine Anforderung, die eine Authentifizierung des Benutzers erfordert.  
  
2.  WIF leitet den Benutzer an den Identitätsanbieter um. Nach der Authentifizierung wird die Anwendungsanforderung mit einem verknüpften Sicherheitstoken durchgeführt, das den Benutzer mit Ansprüchen darstellt. WIF ordnet diese Ansprüche dem Prinzipal zu, der den Benutzer darstellt.  
  
3.  Die Anwendung übergibt die Ansprüche an den Entscheidungslogikmechanismus. Dabei kann es sich um Code im Arbeitsspeicher, einen Aufruf eines Webdiensts, eine Abfrage einer Datenbank, ein hoch entwickeltes Regelmodul oder die Verwendung von ClaimsAuthorizationManager handeln.  
  
4.  Der Entscheidungsmechanismus berechnet das Ergebnis auf Grundlage der Ansprüche.  
  
5.  Der Zugriff wird gewährt, wenn das Ergebnis "true" ist, und verweigert, wenn es "false" ist. Beispielsweise könnte die Regel lauten, dass der Benutzer mindestens 21 Jahre alt sein und in Hessen leben muss.  
  
 <xref:System.Security.Claims.ClaimsAuthorizationManager> ist nützlich, um die Entscheidungslogik für die anspruchsbasierte Autorisierung in Anwendungen zu externalisieren. ClaimsAuthorizationManager ist eine WIF-Komponente, die im Lieferumfang von .NET 4.5 enthalten ist. Mit ClaimsAuthorizationManager können Sie eingehende Anforderungen abfangen und eine Logik Ihrer Wahl implementieren, um Autorisierungsentscheidungen auf der Basis eingehender Ansprüche zu treffen. Dies ist wichtig, wenn die Autorisierungslogik geändert werden muss. In diesem Fall beeinträchtigt die Verwendung von ClaimsAuthorizationManager nicht die Integrität der Anwendung. Darüber hinaus wird die Wahrscheinlichkeit eines Anwendungsfehlers aufgrund der Änderung reduziert. Weitere Informationen dazu, wie Sie ClaimsAuthorizationManager zur Implementierung von anspruchsbasierter Zugriffssteuerung verwenden, finden Sie unter [How To: Implement Claims Authorization in a Claims Aware ASP.NET Application Using WIF and ACS (Vorgehensweise: Implementieren von Anspruchsautorisierung in einer Ansprüche unterstützenden ASP.NET-Anwendung mithilfe von WIF und ACS)](http://go.microsoft.com/fwlink/?LinkID=247446).
