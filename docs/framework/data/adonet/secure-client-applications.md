---
title: Sichere Clientanwendungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1218cda46a6a901c3dbf9fb11333b04d0133df42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="secure-client-applications"></a>Sichere Clientanwendungen
Anwendungen bestehen in der Regel aus vielen Teilen, die alle so geschützt werden müssen, dass keine Daten verloren gehen oder das System nicht anderweitig gefährdet wird. Durch das Erstellen sicherer Benutzeroberflächen lassen sich viele Probleme vermeiden, weil Angreifer damit bereits blockiert werden, bevor sie überhaupt auf Daten oder Systemressourcen zugreifen können.  
  
## <a name="validate-user-input"></a>Validieren von Benutzereingaben  
 Beim Erstellen einer Anwendung mit Datenzugriff müssen Sie davon ausgehen, dass jede Benutzereingabe an sich schädlich sein kann, solange nichts Gegenteiliges bewiesen ist. Andernfalls gefährden Sie Ihre Anwendung. In .NET Framework gibt es Klassen, mit deren Hilfe Sie für Eingabesteuerelemente festlegen können, wie gültige Werte aussehen müssen. So können Sie z. B. festlegen, wie viele Buchstaben maximal eingegeben werden dürfen. Ereignishooks ermöglichen es Ihnen, Prozeduren zum Prüfen der Gültigkeit von Werten zu schreiben. Benutzereingabedaten können validiert und stark typisiert werden, sodass die Anwendung weniger anfällig für Skriptexploits und SQL Injection-Angriffe ist.  
  
> [!IMPORTANT]
>  Zusätzlich muss die Benutzereingabe sowohl an der Datenquelle als auch in der Clientanwendung validiert werden, da Angreifer ansonsten Ihre Anwendung umgehen und die Datenquelle direkt angreifen könnten.  
  
 [Sicherheit und Benutzereingaben](../../../../docs/standard/security/security-and-user-input.md)  
 Beschreibt die Vorgehensweise bei kleinen und potenziell gefährlichen Fehlern im Zusammenhang mit der Benutzereingabe.  
  
 [Validieren von Benutzereingaben in ASP.NET Web Pages](http://msdn.microsoft.com/library/4ad3dacb-89e0-4cee-89ac-40a3f2a85461)  
 Enthält eine Übersicht über das Validieren der Benutzereingabe mit ASP.NET-Validierungssteuerelementen.  
  
 [Benutzereingaben in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 Enthält Links und Informationen zum Validieren von Eingaben mit Maus und Tastatur in einer Windows Forms-Anwendung.  
  
 [Reguläre Ausdrücke von .NET Framework](../../../../docs/standard/base-types/regular-expressions.md)  
 Beschreibt die Verwendung der <xref:System.Text.RegularExpressions.Regex>-Klasse, mit der die Gültigkeit der Benutzereingabe geprüft werden kann.  
  
## <a name="windows-applications"></a>Windows-Anwendungen  
 In der Vergangenheit wurden Windows-Anwendungen i. d. R. mit vollständigen Berechtigungen ausgeführt. .NET Framework stellt mit der Codezugriffssicherheit (Code Access Security, CAS) die Infrastruktur bereit, die erforderlich ist, um die Ausführung von Code in Windows-Anwendungen zu beschränken. CAS allein reicht aber zum Schutz Ihrer Anwendung nicht aus.  
  
 [Sicherheit in Windows Forms](../../../../docs/framework/winforms/windows-forms-security.md)  
 Erläutert das Sichern von Windows Forms-Anwendungen und stellt Links zu verwandten Themen bereit.  
  
 [Windows Forms und nicht verwaltete Anwendungen](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)  
 Beschreibt die Interaktion mit nicht verwalteten Anwendungen in einer Windows Forms-Anwendung.  
  
 [ClickOnce-Bereitstellung für Windows Forms-Anwendungen](http://msdn.microsoft.com/en-us/34d8c770-48f2-460c-8d67-4ea5684511df)  
 Beschreibt die Verwendung einer `ClickOnce`-Bereitstellung in einer Windows Forms-Anwendung und erläutert die Auswirkungen auf die Sicherheit.  
  
## <a name="aspnet-and-xml-web-services"></a>ASP.NET und XML-Webdienste  
 ASP.NET-Anwendungen müssen im Allgemeinen den Zugriff auf einige Teile der Website einschränken und stellen andere Mechanismen für Datenschutz und die Sicherheit von Websites bereit. Über diese Links erhalten Sie nützliche Informationen zum Absichern Ihrer ASP.NET-Anwendung.  
  
 XML-Webdienste stellen Daten bereit, die von ASP.NET-Anwendungen, Windows Forms-Anwendungen oder anderen Webdiensten genutzt werden können. Um die Sicherheit des Webdiensts und die der Clientanwendung müssen Sie sich selbst kümmern.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[NIB: ASP.NET-Sicherheit](http://msdn.microsoft.com/en-us/04b37532-18d9-40b4-8e5f-ee09a70b311d)|Erläutert das Sichern von ASP.NET-Anwendungen.|  
|[Sichern mithilfe von ASP.NET erstellte XML-Webdiensten](http://msdn.microsoft.com/en-us/354b2ab1-2782-4542-b32a-dc560178b90c)|Veranschaulicht das Implementieren von Sicherheit für einen ASP.NET-Webdienst.|  
|[Script-Exploits-Übersicht](http://msdn.microsoft.com/library/772c7312-211a-4eb3-8d6e-eec0aa1dcc07)|Erläutert, wie Sie sich vor Angriffen mit Skriptexploits schützen können, bei denen versucht wird, bösartige Zeichen in eine Webseite einzufügen.|  
|[NIB: Basic Sicherheitsmaßnahmen für ASP.NET-Webanwendungen](http://msdn.microsoft.com/en-us/94a52ab8-731d-417e-b997-721baf43df38)|Enthält allgemeine Sicherheitsinformationen und Links zu weiteren Erläuterungen.|  
  
## <a name="remoting"></a>Remoting  
 Mit .NET-Remoting können Sie auf einfache Weise weit verteilte Anwendungen erstellen, wobei sich die einzelnen Anwendungskomponenten auf demselben Computer oder weltweit an verschiedenen Standorten befinden können. Sie können Clientanwendungen erstellen, die Objekte in anderen Prozessen auf demselben Computer oder auf einem beliebigen anderen Computer im Netzwerk verwenden. Sie können .NET Remoting auch für die Kommunikation mit anderen Anwendungsdomänen im selben Prozess verwenden.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Konfiguration des Remoteanwendungen](http://msdn.microsoft.com/en-us/92c0c097-d984-4315-835b-7490ecdf1097)|Erläutert, wie Sie Remoting-Anwendungen so konfigurieren können, dass allgemeine Probleme vermieden werden.|  
|[Sicherheit in Remoting](http://msdn.microsoft.com/en-us/9574262c-d4b1-41c5-8600-24ff147c0add)|Beschreibt die Authentifizierung und Verschlüsselung und enthält darüber hinaus weitere Sicherheitsthemen im Zusammenhang mit Remoting.|  
|[Sicherheit und Remoting-Überlegungen](../../../../docs/framework/misc/security-and-remoting-considerations.md)|Beschreibt Sicherheitsprobleme mit geschützten Objekten und dem anwendungsdomänenübergreifenden Arbeiten.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Empfehlungen für die Daten für Zugriffsmethoden](http://msdn.microsoft.com/en-us/72411f32-d12a-4de8-b961-e54fca7faaf5)  
 [Sichern von Anwendungen](/visualstudio/ide/securing-applications)  
 [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
