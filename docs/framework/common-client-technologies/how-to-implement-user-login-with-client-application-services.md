---
title: 'Gewusst wie: Implementieren einer Benutzeranmeldung mit Clientanwendungsdiensten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating users [client application services]
- validation [.NET Framework], client application services
- client application services, authenticate users
ms.assetid: 5431a671-eb02-4e18-a651-24764fccec9a
ms.openlocfilehash: 1b1c5bebb5bd94f0a56dc6da303ef2503ab6dd4f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743809"
---
# <a name="how-to-implement-user-login-with-client-application-services"></a>Gewusst wie: Implementieren einer Benutzeranmeldung mit Clientanwendungsdiensten
Sie können Clientanwendungsdienste verwenden, um Benutzer durch einen vorhandenen [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]-Profildienst zu überprüfen. Informationen zum Einrichten des [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]-Profildiensts finden Sie unter [Verwenden der Formularauthentifizierung mit Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e).  
  
 Die folgenden Verfahren beschreiben, wie Benutzer über den Authentifizierungsdienst überprüft werden können, wenn Ihre Anwendung entsprechend auf die Anwendung eines der Client-Authentifizierungs-Dienstanbieter konfiguriert ist. Weitere Informationen finden Sie unter [How to: Configure Client Application Services](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md).  
  
 Normalerweise nehmen Sie die gesamte Validierung per `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType>-Methode vor. Bei dieser Methode wird die Interaktion mit dem Authentifizierungsdienst über den konfigurierten Authentifizierungsanbieter verwaltet. Weitere Informationen finden Sie unter [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md).  
  
 Für die Schritte zur Formularauthentifizierung ist der Zugriff auf einen laufenden [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)]-Authentifizierungsdienst erforderlich. Einen Leitfaden zu den End-to-End-Testverfahren der Clientanwendungsdienst-Funktionen finden Sie unter [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
### <a name="to-authenticate-a-user-with-forms-authentication-using-a-membership-credentials-provider"></a>So authentifizieren Sie einen Benutzer mit der Formularauthentifizierung unter Verwendung eines Mitgliedschaftsdaten-Anbieters:  
  
1.  Implementieren Sie die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>-Schnittstelle. Im folgenden Codebeispiel wird eine <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A?displayProperty=nameWithType> -Implementierung für eine Anmeldungs-Dialogfeldklasse, die von <xref:System.Windows.Forms.Form?displayProperty=nameWithType> stammt, angezeigt. Dieses Dialogfeld enthält Textfelder für den Benutzernamen und das Kennwort sowie ein Kontrollkästchen „Merken“. Wenn der Client-Authentifizierungsanbieter die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A>-Methode aufruft, wird das Formular angezeigt. Wenn der Benutzer die Informationen in das Anmeldedialogfeld eingibt, und auf OK klickt, werden die angegebenen Werte in ein neues <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>-Objekt ausgegeben.  
  
     [!code-csharp[ClientApplicationServices#210](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Login.cs#210)]
     [!code-vb[ClientApplicationServices#210](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Login.vb#210)]  
  
2.  Rufen Sie die `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType> -Methode auf, und fügen Sie leere Zeichenfolgen als Parameterwerte ein. Wenn Sie leere Zeichenfolgen angeben, ruft diese Methode intern die <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider.GetCredentials%2A>-Methode für die für Ihre Anwendung konfigurierten Anbieter von Anmeldeinformationen für die Anwendung auf. Im folgenden Codebeispiel wird diese Methode verwendet, um den Zugriff auf eine Windows Forms-Vollanwendung einzuschränken. Sie können diesen Code zum Hinzufügen eines <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>-Handlers hinzufügen.  
  
     [!code-csharp[ClientApplicationServices#317](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#317)]
     [!code-vb[ClientApplicationServices#317](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#317)]  
  
### <a name="to-authenticate-a-user-with-forms-authentication-without-using-a-membership-credentials-provider"></a>So authentifizieren Sie einen Benutzer mit der Formularauthentifizierung ohne Verwendung eines Mitgliedschaftsdaten-Anbieters:  
  
-   Rufen Sie die `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType>-Methode auf, und fügen Sie die Benutzernamens- und die Kennwortwerte ein, die Sie vom Benutzer erhalten haben.  
  
     [!code-csharp[ClientApplicationServices#318](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#318)]
     [!code-vb[ClientApplicationServices#318](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#318)]  
  
### <a name="to-authenticate-a-user-with-windows-authentication"></a>So authentifizieren Sie einen Benutzer mithilfe der Windows-Authentifizierung:  
  
-   Rufen Sie die `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType>-Methode auf, und fügen Sie leere Zeichenfolgen als Parameter ein. Bei diesem Methodenaufruf werden immer `true` ausgegeben, und bei dem Aufruf wird im Cookie-Cache des Benutzers ein Cookie hinzugefügt, welcher die Windows-Identität enthält.  
  
     [!code-csharp[ClientApplicationServices#319](../../../samples/snippets/csharp/VS_Snippets_Winforms/ClientApplicationServices/CS/Class1.cs#319)]
     [!code-vb[ClientApplicationServices#319](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ClientApplicationServices/VB/Class1.vb#319)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Der Beispielcode in diesem Thema veranschaulicht die einfachsten Verwendungsmöglichkeiten der Authentifizierung in einer Windows-Clientanwendung. Beim Aufrufen der `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=nameWithType>-Methode mit den Clientanwendungsdiensten und der Formularauthentifizierung kann Ihr Code jedoch Folgendes auslösen: <xref:System.Net.WebException>. Dies gibt an, dass der Authentifizierungsdienst nicht verfügbar ist. Ein Beispiel für den Umgang mit dieser Ausnahme finden Sie unter [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services.md)  
 [Übersicht über Clientanwendungsdienste](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 [Vorgehensweise: Konfigurieren von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 [Exemplarische Vorgehensweise: Verwenden von Clientanwendungsdiensten](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 [Verwenden der Formularauthentifizierung mit Microsoft Ajax](http://msdn.microsoft.com/library/c50f7dc5-323c-4c63-b4f3-96edfc1e815e)
