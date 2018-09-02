---
title: 'Vorgehensweise: Angeben von Clientanmeldeinformationen für eine Datendienstanforderung (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing requests
ms.assetid: 1632f9af-e45f-4363-9222-03823daa8e28
ms.openlocfilehash: d0fbf01de05a02c03782af9e392a79b6dd3e8bee
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402520"
---
# <a name="how-to-specify-client-credentials-for-a-data-service-request-wcf-data-services"></a>Vorgehensweise: Angeben von Clientanmeldeinformationen für eine Datendienstanforderung (WCF Data Services)
In der Standardeinstellung werden von der Clientbibliothek keine Anmeldeinformationen bereitgestellt, wenn eine Anforderung an einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Dienst gesendet wird. Sie können jedoch angeben, dass Anmeldeinformationen zum Authentifizieren von Anforderungen an den Datendienst gesendet werden, indem Sie <xref:System.Net.NetworkCredential> für die <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A>-Eigenschaft des <xref:System.Data.Services.Client.DataServiceContext> angeben. Weitere Informationen finden Sie unter [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md). Das Beispiel in diesem Thema veranschaulicht das explizite Angeben von Anmeldeinformationen, die beim Anfordern von Daten vom Datendienst vom [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]-Client verwendet werden.  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Können Sie auch die [Northwind-beispieldatendienst](https://go.microsoft.com/fwlink/?LinkId=187426) auf veröffentlichte die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Website, diese Beispieldaten Dienst ist schreibgeschützt, und um Änderungen zu speichern versuchen, einen Fehler zurück. Die beispieldatendienste auf der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Website lassen die anonyme Authentifizierung.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird aus der CodeBehind-Seite für eine Extensible Application Markup Language (XAML)-Datei, die der Hauptseite der Windows Presentation Framework-Anwendung ist. In diesem Beispiel werden mit einer `LoginWindow`-Instanz Anmeldeinformationen für die Authentifizierung vom Benutzer gesammelt, die dann beim Senden einer Anforderung an den Datendienst verwendet werden.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/clientcredentials.xaml.cs#clientcredentials)]  
 [!code-vb[Astoria Northwind Client#ClientCredentials](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/clientcredentials.xaml.vb#clientcredentials)]
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code definiert die Hauptseite der WPF-Anwendung.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/clientcredentials.xaml#clientcredentialsxaml)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel stammt aus der CodeBehind-Seite für das Fenster, mit dem die Anmeldeinformationen für die Authentifizierung vom Benutzer gesammelt werden, bevor eine Anforderung an den Datendienst gesendet wird.  
  
 [!code-csharp[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/clientcredentialslogin.xaml.cs#clientcredentialslogin)]  
 [!code-vb[Astoria Northwind Client#ClientCredentialsLogin](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/clientcredentialslogin.xaml.vb#clientcredentialslogin)]
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code definiert das Anmeldefenster der WPF-Anwendung.  
  
 [!code-xaml[Astoria Northwind Client#ClientCredentialsLoginXaml](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/clientcredentialslogin.xaml#clientcredentialsloginxaml)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die folgenden Überlegungen zur Sicherheit gelten für das Beispiel in diesem Thema:  
  
-   Um zu überprüfen, ob die angegebenen Anmeldeinformationen in diesem Beispiel funktionieren, muss für den Northwind-Datendienst ein anderes Authentifizierungsschema als der anonyme Zugriff verwendet werden. Andernfalls werden von der Website, die den Datendienst hostet, keine Anmeldeinformationen angefordert.  
  
-   Benutzeranmeldeinformationen sollten nur während der Ausführung angefordert und nicht zwischengespeichert werden. Anmeldeinformationen müssen immer sicher gespeichert werden.  
  
-   Mittels Standard- und Digestauthentifizierung gesendete Daten sind nicht verschlüsselt und daher für Angreifer sichtbar. Anmeldeinformationen für die Standardauthentifizierung (Benutzername und Kennwort) werden zudem in Klartext gesendet und können abgefangen werden.  
  
 Weitere Informationen finden Sie unter [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
