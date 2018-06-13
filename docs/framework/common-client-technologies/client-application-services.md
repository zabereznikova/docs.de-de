---
title: Clientanwendungsdienste
ms.date: 03/30/2017
helpviewer_keywords:
- role-based security [.NET Framework], client application services
- client application services
- credentials [.NET Framework]
- Windows-based applications, client application services
- application settings, client application services
- profiles [ASP.NET], client application services
- logins [client application services]
- sharing information and functionality [client application services]
- Web settings [client application services]
- authentication [ASP.NET], client application services
- ASP.NET services, client application services
- client applications, ASP.NET services
- roles [.NET Framework], client application services
- client application services, about client application services
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
ms.openlocfilehash: d67b7467bdacdfca054d0ecd11a81c7d25b158f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743224"
---
# <a name="client-application-services"></a>Clientanwendungsdienste
Clientanwendungsdienste erleichtern Ihnen Erstellung von Windows-basierten Anwendungen, die die [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]-Anmelde-, -Rollen- und -Profilanwendungsdienste verwenden, die in den Microsoft ASP.NET 2.0 AJAX-Erweiterungen enthalten sind. Diese Dienste ermöglichen mehreren web- und Windows-basierten Anwendungen die gemeinsame Nutzung von Benutzerinformationen und Benutzerverwaltungsfunktionen von einem einzelnen Server aus. Beispielsweise können Sie mithilfe dieser Dienste folgende Aufgaben ausführen:  
  
-   Authentifizieren von Benutzern. Mithilfe des Authentifizierungsdiensts können Sie die Identität eines Benutzers überprüfen.  
  
-   Bestimmen der Rolle oder Rollen eines authentifizierten Benutzers. Mithilfe des Rollendiensts können Sie die Benutzeroberfläche Ihrer Anwendung in Abhängigkeit von der Rolle des Benutzers ändern. Beispielsweise können Sie zusätzliche Funktionen für Benutzer bereitstellen, die in einer Administratorrolle sind.  
  
-   Speichern von und Zugreifen auf benutzerspezifische Anwendungseinstellungen auf dem Server. Mithilfe des Webeinstellungendiensts (auch als Profildienst bekannt) können Sie Einstellungen zwischen mehreren Anwendungen und Speicherorten gemeinsam nutzen.  
  
 Clientanwendungsdienste nutzen das Erweiterbarkeitsmodell des Webdiensts durch Clientdienstanbieter, die Sie in Ihren Anwendungskonfigurationsdateien angeben können. Diese Dienstanbieter umfassen Offlinefunktionalitäten, die einen lokalen Cache für Authentifizierung, Rollen und Einstellungsdaten verwenden, wenn keine Netzwerkverbindung verfügbar ist.  
  
 Weitere Informationen zu den [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]-Anwendungsdiensten finden Sie unter [Übersicht über ASP.NET-Anwendungsdienste](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 Beschreibt die Funktionen, die durch die Clientanwendungs-Dienstanbieter verfügbar sind.  
  
 [Vorgehensweise: Konfigurieren von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 Beschreibt, wie Sie den Visual Studio-Projekt-Designer zum Aktivieren und Konfigurieren von Anwendungsdiensten verwenden. Beschreibt außerdem die entsprechenden Änderungen an Ihrer Datei "App.config".  
  
 [Gewusst wie: Implementieren einer Benutzeranmeldung mit Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 Beschreibt, wie Sie einen Benutzer überprüfen, wenn Ihre Anwendung so konfiguriert ist, dass sie einen Clientauthentifizierungs-Dienstanbieter verwendet.  
  
 [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 Beschreibt, wie alle Funktionen von Clientanwendungsdiensten in einer einzigen Anwendung kombiniert werden. Diese exemplarische Vorgehensweise bietet Anleitungen von Anfang bis Ende. Beispielsweise enthält sie Anweisungen zum Erstellen einer ASP.NET-Webdienstanwendung, mit der Sie Clientanwendungsdienste testen können.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die ASP.NET-Anwendungsdienste](http://msdn.microsoft.com/library/1162e529-0d70-44b2-b3ab-83e60c695013)  
 [Verwenden der Formularauthentifizierung mit Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)  
 [Verwenden von Rolleninformationen mit Microsoft Ajax](http://msdn.microsoft.com/library/280f6ad9-ba1a-4fc9-b0cc-22e39e54a82d)  
 [Verwenden von Profilinformationen mit Microsoft Ajax](http://msdn.microsoft.com/library/91239ae6-d01c-4f4e-a433-eb9040dbed61)  
 [Authentifizierung in ASP.NET](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1)  
 [Verwalten der Autorisierung mithilfe von Rollen](http://msdn.microsoft.com/library/01954ce4-39a2-487f-8153-a69f6f6f3195)    
 [Übersicht über Anwendungseinstellungen](../../../docs/framework/winforms/advanced/application-settings-overview.md)
