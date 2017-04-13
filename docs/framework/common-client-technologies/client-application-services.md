---
title: "Clientanwendungsdienste | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungseinstellungen, Clientanwendungdienste"
  - "ASP.NET-Dienste, Clientanwendungdienste"
  - "Authentifizierung [ASP.NET], Clientanwendungdienste"
  - "Clientanwendungdienste"
  - "Clientanwendungdienste, Informationen zum Verwenden von Clientanwendungdiensten"
  - "Clientanwendungen, ASP.NET-Dienste"
  - "Anmeldeinformationen [.NET Framework]"
  - "Anmeldungen [Clientanwendungdienste]"
  - "Profile [ASP.NET], Clientanwendungdienste"
  - "Rollenbasierte Sicherheit [.NET Framework], Clientanwendungdienste"
  - "Rollen [.NET Framework], Clientanwendungdienste"
  - "Freigeben von Informationen und Funktionen [Clientanwendungdienste]"
  - "Webeinstellungen [Clientanwendungdienste]"
  - "Windows-basierte Anwendungen, Clientanwendungdienste"
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Clientanwendungsdienste
Clientanwendungsdienste erleichtern Ihnen Erstellung von Windows\-basierten Anwendungen, die die [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]\-Anmelde\-, \-Rollen\- und \-Profilanwendungsdienste verwenden, die in den Microsoft ASP.NET 2.0 AJAX\-Erweiterungen enthalten sind.  Diese Dienste ermöglichen mehreren web\- und Windows\-basierten Anwendungen die gemeinsame Nutzung von Benutzerinformationen und Benutzerverwaltungsfunktionen von einem einzelnen Server aus.  Beispielsweise können Sie mithilfe dieser Dienste folgende Aufgaben ausführen:  
  
-   Authentifizieren von Benutzern.  Mithilfe des Authentifizierungsdiensts können Sie die Identität eines Benutzers überprüfen.  
  
-   Bestimmen der Rolle oder Rollen eines authentifizierten Benutzers.  Mithilfe des Rollendiensts können Sie die Benutzeroberfläche Ihrer Anwendung in Abhängigkeit von der Rolle des Benutzers ändern.  Beispielsweise können Sie zusätzliche Funktionen für Benutzer bereitstellen, die in einer Administratorrolle sind.  
  
-   Speichern von und Zugreifen auf benutzerspezifische Anwendungseinstellungen auf dem Server.  Mithilfe des Webeinstellungendiensts \(auch als Profildienst bekannt\) können Sie Einstellungen zwischen mehreren Anwendungen und Speicherorten gemeinsam nutzen.  
  
 Clientanwendungsdienste nutzen das Erweiterbarkeitsmodell des Webdiensts durch Clientdienstanbieter, die Sie in Ihren Anwendungskonfigurationsdateien angeben können.  Diese Dienstanbieter umfassen Offlinefunktionalitäten, die einen lokalen Cache für Authentifizierung, Rollen und Einstellungsdaten verwenden, wenn keine Netzwerkverbindung verfügbar ist.  
  
 Weitere Informationen zu den [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]\-Anwendungsdiensten finden Sie unter [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md).  
  
## In diesem Abschnitt  
 [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 Beschreibt die Funktionen, die durch die Clientanwendungs\-Dienstanbieter verfügbar sind.  
  
 [Gewusst wie: Konfigurieren von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 Beschreibt, wie Sie den [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]\-Projekt\-Designer zum Aktivieren und Konfigurieren von Anwendungsdiensten verwenden.  Beschreibt außerdem die entsprechenden Änderungen an Ihrer Datei "App.config".  
  
 [Gewusst wie: Implementieren einer Benutzeranmeldung mit Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 Beschreibt, wie Sie einen Benutzer überprüfen, wenn Ihre Anwendung so konfiguriert ist, dass sie einen Clientauthentifizierungs\-Dienstanbieter verwendet.  
  
 [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 Beschreibt, wie alle Funktionen von Clientanwendungsdiensten in einer einzigen Anwendung kombiniert werden.  Diese exemplarische Vorgehensweise bietet Anleitungen von Anfang bis Ende.  Beispielsweise enthält sie Anweisungen zum Erstellen einer ASP.NET\-Webdienstanwendung, mit der Sie Clientanwendungsdienste testen können.  
  
## Referenz  
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
  
## Siehe auch  
 [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md)   
 [Using Forms Authentication with Microsoft Ajax](../Topic/Using%20Forms%20Authentication%20with%20Microsoft%20Ajax.md)   
 [Using Roles Information with Microsoft Ajax](../Topic/Using%20Roles%20Information%20with%20Microsoft%20Ajax.md)   
 [Using Profile Information with Microsoft Ajax](../Topic/Using%20Profile%20Information%20with%20Microsoft%20Ajax.md)   
 [ASP.NET Authentication](../Topic/ASP.NET%20Authentication.md)   
 [Managing Authorization Using Roles](../Topic/Managing%20Authorization%20Using%20Roles.md)   
 [OLD NIB: Managing Application Settings](http://msdn.microsoft.com/de-de/7de3c3bd-e0dc-4e75-a1aa-7b0ecfaac4fc)   
 [Übersicht über Anwendungseinstellungen](../../../docs/framework/winforms/advanced/application-settings-overview.md)