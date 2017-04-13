---
title: "Vorgehensweise: Angeben von Clientanmeldeinformationen f&#252;r eine Datendienstanforderung (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Anpassen von Anforderungen"
ms.assetid: 1632f9af-e45f-4363-9222-03823daa8e28
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Vorgehensweise: Angeben von Clientanmeldeinformationen f&#252;r eine Datendienstanforderung (WCF Data Services)
In der Standardeinstellung werden von der Clientbibliothek keine Anmeldeinformationen bereitgestellt, wenn eine Anforderung an einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Dienst gesendet wird.  Sie können jedoch angeben, dass Anmeldeinformationen zum Authentifizieren von Anforderungen an den Datendienst gesendet werden, indem Sie <xref:System.Net.NetworkCredential> für die <xref:System.Data.Services.Client.DataServiceContext.Credentials%2A>\-Eigenschaft des <xref:System.Data.Services.Client.DataServiceContext> angeben.  Weitere Informationen finden Sie unter [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  Das Beispiel in diesem Thema veranschaulicht das explizite Angeben von Anmeldeinformationen, die beim Anfordern von Daten vom Datendienst vom [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Client verwendet werden.  
  
 Im Beispiel in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Client\-Datendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  Sie können auch den öffentlichen [Northwind\-Beispieldatendienst](http://go.microsoft.com/fwlink/?LinkId=187426) auf der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Website verwenden. Dieser Beispieldatendienst ist schreibgeschützt. Wenn Sie versuchen, Änderungen zu speichern, wird ein Fehler zurückgegeben.  Die Beispieldatendienste auf der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Website lassen die anonyme Authentifizierung zu.  
  
## Beispiel  
 Das folgende Beispiel stammt aus der CodeBehind\-Seite für eine XAML\-Datei \(Extensible Application Markup Language\), bei der es sich um die Hauptseite der Windows Presentation Framework\-Anwendung handelt.  In diesem Beispiel werden mit einer `LoginWindow`\-Instanz Anmeldeinformationen für die Authentifizierung vom Benutzer gesammelt, die dann beim Senden einer Anforderung an den Datendienst verwendet werden.  
  
  
  
## Beispiel  
 Der folgende XAML\-Code definiert die Hauptseite der WPF\-Anwendung.  
  
  
  
## Beispiel  
 Das folgende Beispiel stammt aus der CodeBehind\-Seite für das Fenster, mit dem die Anmeldeinformationen für die Authentifizierung vom Benutzer gesammelt werden, bevor eine Anforderung an den Datendienst gesendet wird.  
  
  
  
## Beispiel  
 Der folgende XAML\-Code definiert das Anmeldefenster der WPF\-Anwendung.  
  
  
  
## .NET Framework-Sicherheit  
 Die folgenden Überlegungen zur Sicherheit gelten für das Beispiel in diesem Thema:  
  
-   Um zu überprüfen, ob die angegebenen Anmeldeinformationen in diesem Beispiel funktionieren, muss für den Northwind\-Datendienst ein anderes Authentifizierungsschema als der anonyme Zugriff verwendet werden.  Andernfalls werden von der Website, die den Datendienst hostet, keine Anmeldeinformationen angefordert.  
  
-   Benutzeranmeldeinformationen sollten nur während der Ausführung angefordert und nicht zwischengespeichert werden.  Anmeldeinformationen müssen immer sicher gespeichert werden.  
  
-   Mittels Standard\- und Digestauthentifizierung gesendete Daten sind nicht verschlüsselt und daher für Angreifer sichtbar.  Anmeldeinformationen für die Standardauthentifizierung \(Benutzername und Kennwort\) werden zudem in Klartext gesendet und können abgefangen werden.  
  
 Weitere Informationen finden Sie unter [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).  
  
## Siehe auch  
 [Sichern von WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)   
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)