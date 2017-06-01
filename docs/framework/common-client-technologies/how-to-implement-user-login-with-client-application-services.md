---
title: "Gewusst wie: Implementieren einer Benutzeranmeldung mit Clientanwendungsdiensten | Microsoft Docs"
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
  - "Clientanwendungdienste, Authentifizieren von Benutzern"
  - "Überprüfen von Benutzern [Clientanwendungsdienste]"
  - "Überprüfung [.NET Framework], Clientanwendungdienste"
ms.assetid: 5431a671-eb02-4e18-a651-24764fccec9a
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Implementieren einer Benutzeranmeldung mit Clientanwendungsdiensten
Sie können Clientanwendungsdienste verwenden, um Benutzer durch einen vorhandenen [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]\-Profildienst zu überprüfen.  Informationen zum Einrichten des [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]\-Profildiensts finden Sie unter [Using Forms Authentication with Microsoft Ajax](../Topic/Using%20Forms%20Authentication%20with%20Microsoft%20Ajax.md).  
  
 Die folgenden Verfahren beschreiben, wie Benutzer über den Authentifizierungsdienst überprüft werden können, wenn Ihre Anwendung entsprechend auf die Anwendung eines der Client\-Authentifizierungs\-Dienstanbieter konfiguriert ist.  Weitere Informationen finden Sie unter [Gewusst wie: Konfigurieren von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
 Normalerweise nehmen Sie die gesamte Überprüfung per `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName>\-Methode vor.  Bei dieser Methode wird die Interaktion mit dem Authentifizierungsdienst über den konfigurierten Authentifizierungsanbieter verwaltet.  Weitere Informationen finden Sie unter [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md).  
  
 Für die Schritte zur Formularauthentifizierung ist der Zugriff auf einen laufenden [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]\-Authentifizierungsdienst erforderlich.  Einen Leitfaden zu den End\-to\-End\-Testverfahren der  Clientanwendungsdienst\-Features finden Sie unter [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
### So authentifizieren Sie einen Benutzer mit der Formularauthentifizierung unter Verwendung eines Mitgliedschaftsdaten\-Anbieters:  
  
1.  Implementieren Sie die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>\-Schnittstelle.  Im folgenden Codebeispiel wird eine <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=fullName> \-Implementierung für eine Anmeldungs\-Dialogfeldklasse, die von <xref:System.Windows.Forms.Form?displayProperty=fullName> stammt, angezeigt.  Dieses Dialogfeld enthält Textfelder für den Benutzernamen und das Kennwort sowie ein Kontrollkästchen „Merken“.  Wenn der Client\-Authentifizierungsanbieter die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A>\-Methode aufruft, wird das Formular angezeigt.  Wenn der Benutzer die Informationen in das Anmeldedialogfeld eingibt, und auf OK klickt, werden die angegebenen Werte in ein neues <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>\-Objekt ausgegeben.  
  
     [!code-csharp[ClientApplicationServices#210](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#210)]
     [!code-vb[ClientApplicationServices#210](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#210)]  
  
2.  Rufen Sie die `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> \-Methode auf, und fügen Sie leere Zeichenfolgen als Parameterwerte ein.  Wenn Sie leere Zeichenfolgen angeben, ruft diese Methode intern die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A>\-Methode für die für Ihre Anwendung konfigurierten Anbieter von Anmeldeinformationen für die Anwendung auf.  Im folgenden Codebeispiel wird diese Methode verwendet, um den Zugriff auf eine Windows Forms\-Vollanwendung einzuschränken.  Sie können diesen Code zum Hinzufügen eines <xref:System.Windows.Forms.Form.Load?displayProperty=fullName>\-Handlers hinzufügen.  
  
     [!code-csharp[ClientApplicationServices#317](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#317)]
     [!code-vb[ClientApplicationServices#317](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#317)]  
  
### So authentifizieren Sie einen Benutzer mit der Formularauthentifizierung ohne Verwendung eines Mitgliedschaftsdaten\-Anbieters:  
  
-   Rufen Sie die `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName>\-Methode auf, und fügen Sie die Benutzernamens\- und die Kennwortwerte ein, die Sie vom Benutzer erhalten haben.  
  
     [!code-csharp[ClientApplicationServices#318](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#318)]
     [!code-vb[ClientApplicationServices#318](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#318)]  
  
### So authentifizieren Sie einen Benutzer mithilfe der Windows\-Authentifizierung:  
  
-   Rufen Sie die `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName>\-Methode auf, und fügen Sie leere Zeichenfolgen als Parameter ein.  Bei diesem Methodenaufruf werden immer `true` ausgegeben, und bei dem Aufruf wird im Cookie\-Cache des Benutzers ein Cookie hinzugefügt, welcher die Windows\-Identität enthält.  
  
     [!code-csharp[ClientApplicationServices#319](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#319)]
     [!code-vb[ClientApplicationServices#319](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#319)]  
  
## Robuste Programmierung  
 Der Beispielcode in diesem Thema veranschaulicht die einfachsten Verwendungsmöglichkeiten der Authentifizierung in einer Windows\-Clientanwendung.  Beim Aufrufen der `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName>\-Methode mit den Clientanwendung Diensten und der Formularauthentifizierung kann Ihr Code jedoch Folgendes auslösen: <xref:System.Net.WebException>.  Dies gibt an, dass der Authentifizierungsdienst nicht verfügbar ist.  Ein Beispiel für den Umgang mit dieser Ausnahme finden Sie unter [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
## Siehe auch  
 [Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services.md)   
 [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md)   
 [Gewusst wie: Konfigurieren von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)   
 [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)   
 [Using Forms Authentication with Microsoft Ajax](../Topic/Using%20Forms%20Authentication%20with%20Microsoft%20Ajax.md)