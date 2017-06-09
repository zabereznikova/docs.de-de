---
title: "Sichere Clientanwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Sichere Clientanwendungen
Anwendungen bestehen in der Regel aus vielen Teilen, die alle so geschützt werden müssen, dass keine Daten verloren gehen oder das System nicht anderweitig gefährdet wird.  Durch das Erstellen sicherer Benutzeroberflächen lassen sich viele Probleme vermeiden, weil Angreifer damit bereits blockiert werden, bevor sie überhaupt auf Daten oder Systemressourcen zugreifen können.  
  
## Validieren von Benutzereingaben  
 Beim Erstellen einer Anwendung mit Datenzugriff müssen Sie davon ausgehen, dass jede Benutzereingabe an sich schädlich sein kann, solange nichts Gegenteiliges bewiesen ist.  Andernfalls gefährden Sie Ihre Anwendung.  In .NET Framework gibt es Klassen, mit deren Hilfe Sie für Eingabesteuerelemente festlegen können, wie gültige Werte aussehen müssen. So können Sie z. B. festlegen, wie viele Buchstaben maximal eingegeben werden dürfen.  Ereignishooks ermöglichen es Ihnen, Prozeduren zum Prüfen der Gültigkeit von Werten zu schreiben.  Benutzereingabedaten können validiert und stark typisiert werden, sodass die Anwendung weniger anfällig für Skriptexploits und SQL Injection\-Angriffe ist.  
  
> [!IMPORTANT]
>  Zusätzlich muss die Benutzereingabe sowohl an der Datenquelle als auch in der Clientanwendung validiert werden,  da Angreifer ansonsten Ihre Anwendung umgehen und die Datenquelle direkt angreifen könnten.  
  
 [Security and User Input](../../../../docs/standard/security/security-and-user-input.md)  
 Beschreibt die Vorgehensweise bei kleinen und potenziell gefährlichen Fehlern im Zusammenhang mit der Benutzereingabe.  
  
 [Validating User Input in ASP.NET Web Pages](../Topic/Validating%20User%20Input%20in%20ASP.NET%20Web%20Pages.md)  
 Enthält eine Übersicht über das Validieren der Benutzereingabe mit ASP.NET\-Validierungssteuerelementen.  
  
 [Benutzereingaben in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 Enthält Links und Informationen zum Validieren von Eingaben mit Maus und Tastatur in einer Windows Forms\-Anwendung.  
  
 [Reguläre Ausdrücke von .NET Framework](../../../../docs/standard/base-types/regular-expressions.md)  
 Beschreibt die Verwendung der <xref:System.Text.RegularExpressions.Regex>\-Klasse, mit der die Gültigkeit der Benutzereingabe geprüft werden kann.  
  
## Windows\-Anwendungen  
 In der Vergangenheit wurden Windows\-Anwendungen i. d. R. mit vollständigen Berechtigungen ausgeführt.  .NET Framework stellt mit der Codezugriffssicherheit \(Code Access Security, CAS\) die Infrastruktur bereit, die erforderlich ist, um die Ausführung von Code in Windows\-Anwendungen zu beschränken.  CAS allein reicht aber zum Schutz Ihrer Anwendung nicht aus.  
  
 [Sicherheit in Windows Forms](../../../../docs/framework/winforms/windows-forms-security.md)  
 Erläutert das Sichern von Windows Forms\-Anwendungen und stellt Links zu verwandten Themen bereit.  
  
 [Windows Forms und nicht verwaltete Anwendungen](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)  
 Beschreibt die Interaktion mit nicht verwalteten Anwendungen in einer Windows Forms\-Anwendung.  
  
 [ClickOnce Deployment for Windows Forms Applications](http://msdn.microsoft.com/de-de/34d8c770-48f2-460c-8d67-4ea5684511df)  
 Beschreibt die Verwendung einer `ClickOnce`\-Bereitstellung in einer Windows Forms\-Anwendung und erläutert die Auswirkungen auf die Sicherheit.  
  
## ASP.NET und XML\-Webdienste  
 ASP.NET\-Anwendungen müssen im Allgemeinen den Zugriff auf einige Teile der Website einschränken und stellen andere Mechanismen für Datenschutz und die Sicherheit von Websites bereit.  Über diese Links erhalten Sie nützliche Informationen zum Absichern Ihrer ASP.NET\-Anwendung.  
  
 XML\-Webdienste stellen Daten bereit, die von ASP.NET\-Anwendungen, Windows Forms\-Anwendungen oder anderen Webdiensten genutzt werden können.  Um die Sicherheit des Webdiensts und die der Clientanwendung müssen Sie sich selbst kümmern.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|---------------|------------------|  
|[NIB: ASP.NET Security](http://msdn.microsoft.com/de-de/04b37532-18d9-40b4-8e5f-ee09a70b311d)|Erläutert das Sichern von ASP.NET\-Anwendungen.|  
|[Securing XML Web Services Created Using ASP.NET](http://msdn.microsoft.com/de-de/354b2ab1-2782-4542-b32a-dc560178b90c)|Veranschaulicht das Implementieren von Sicherheit für einen ASP.NET\-Webdienst.|  
|[Script Exploits Overview](../Topic/Script%20Exploits%20Overview.md)|Erläutert, wie Sie sich vor Angriffen mit Skriptexploits schützen können, bei denen versucht wird, bösartige Zeichen in eine Webseite einzufügen.|  
|[NIB:Basic Security Practices for ASP.NET Web Applications](http://msdn.microsoft.com/de-de/94a52ab8-731d-417e-b997-721baf43df38)|Enthält allgemeine Sicherheitsinformationen und Links zu weiteren Erläuterungen.|  
  
## Remoting  
 Mit .NET\-Remoting können Sie auf einfache Weise weit verteilte Anwendungen erstellen, wobei sich die einzelnen Anwendungskomponenten auf demselben Computer oder weltweit an verschiedenen Standorten befinden können.  Sie können Clientanwendungen erstellen, die Objekte in anderen Prozessen auf demselben Computer oder auf einem beliebigen anderen Computer im Netzwerk verwenden.  Sie können .NET Remoting auch für die Kommunikation mit anderen Anwendungsdomänen im selben Prozess verwenden.  
  
|Ressource|Beschreibung|  
|---------------|------------------|  
|[Configuration of Remote Applications](http://msdn.microsoft.com/de-de/92c0c097-d984-4315-835b-7490ecdf1097)|Erläutert, wie Sie Remoting\-Anwendungen so konfigurieren können, dass allgemeine Probleme vermieden werden.|  
|[Security in Remoting](http://msdn.microsoft.com/de-de/9574262c-d4b1-41c5-8600-24ff147c0add)|Beschreibt die Authentifizierung und Verschlüsselung und enthält darüber hinaus weitere Sicherheitsthemen im Zusammenhang mit Remoting.|  
|[Security and Remoting Considerations](../../../../docs/framework/misc/security-and-remoting-considerations.md)|Beschreibt Sicherheitsprobleme mit geschützten Objekten und dem anwendungsdomänenübergreifenden Arbeiten.|  
  
## Siehe auch  
 [Sichern von ADO.NET\-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Recommendations for Data Access Strategies](http://msdn.microsoft.com/de-de/72411f32-d12a-4de8-b961-e54fca7faaf5)   
 [Sichern von Anwendungen](../Topic/Securing%20Applications.md)   
 [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)