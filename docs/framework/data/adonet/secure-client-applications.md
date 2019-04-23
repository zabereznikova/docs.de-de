---
title: Sichere Clientanwendungen
ms.date: 03/30/2017
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
ms.openlocfilehash: 0c14089247e916b91cb385c7d715cce54acee57c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119612"
---
# <a name="secure-client-applications"></a>Sichere Clientanwendungen
Anwendungen bestehen in der Regel aus vielen Teilen, die alle so geschützt werden müssen, dass keine Daten verloren gehen oder das System nicht anderweitig gefährdet wird. Durch das Erstellen sicherer Benutzeroberflächen lassen sich viele Probleme vermeiden, weil Angreifer damit bereits blockiert werden, bevor sie überhaupt auf Daten oder Systemressourcen zugreifen können.  
  
## <a name="validate-user-input"></a>Validieren von Benutzereingaben  
 Beim Erstellen einer Anwendung mit Datenzugriff müssen Sie davon ausgehen, dass jede Benutzereingabe an sich schädlich sein kann, solange nichts Gegenteiliges bewiesen ist. Andernfalls gefährden Sie Ihre Anwendung. In .NET Framework gibt es Klassen, mit deren Hilfe Sie für Eingabesteuerelemente festlegen können, wie gültige Werte aussehen müssen. So können Sie z. B. festlegen, wie viele Buchstaben maximal eingegeben werden dürfen. Ereignishooks ermöglichen es Ihnen, Prozeduren zum Prüfen der Gültigkeit von Werten zu schreiben. Benutzereingabedaten können validiert und stark typisiert werden, sodass die Anwendung weniger anfällig für Skriptexploits und SQL Injection-Angriffe ist.  
  
> [!IMPORTANT]
>  Zusätzlich muss die Benutzereingabe sowohl an der Datenquelle als auch in der Clientanwendung validiert werden, da Angreifer ansonsten Ihre Anwendung umgehen und die Datenquelle direkt angreifen könnten.  
  
 [Sicherheit und Benutzereingaben](../../../../docs/standard/security/security-and-user-input.md)  
 Beschreibt die Vorgehensweise bei kleinen und potenziell gefährlichen Fehlern im Zusammenhang mit der Benutzereingabe.  
  
 [Überprüfen der Benutzereingabe in ASP.NET-Webseiten](https://docs.microsoft.com/previous-versions/aspnet/7kh55542(v=vs.100))  
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
  
 [ClickOnce-Bereitstellung für Windows Forms](../../winforms/clickonce-deployment-for-windows-forms.md)  
 Beschreibt die Verwendung einer `ClickOnce`-Bereitstellung in einer Windows Forms-Anwendung und erläutert die Auswirkungen auf die Sicherheit.  
  
## <a name="aspnet-and-xml-web-services"></a>ASP.NET und XML-Webdienste  
 ASP.NET-Anwendungen müssen im Allgemeinen den Zugriff auf einige Teile der Website einschränken und stellen andere Mechanismen für Datenschutz und die Sicherheit von Websites bereit. Über diese Links erhalten Sie nützliche Informationen zum Absichern Ihrer ASP.NET-Anwendung.  
  
 XML-Webdienste stellen Daten bereit, die von ASP.NET-Anwendungen, Windows Forms-Anwendungen oder anderen Webdiensten genutzt werden können. Um die Sicherheit des Webdiensts und die der Clientanwendung müssen Sie sich selbst kümmern.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Sichern von ASP.NET-Websites](https://docs.microsoft.com/previous-versions/aspnet/91f66yxt(v=vs.100))|Erläutert das Sichern von ASP.NET-Anwendungen.|  
|[Sichern von mit ASP.NET erstellten XML-Webdienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))|Veranschaulicht das Implementieren von Sicherheit für einen ASP.NET-Webdienst.|  
|[Übersicht über Skriptangriffe](https://docs.microsoft.com/previous-versions/aspnet/w1sw53ds(v=vs.100))|Erläutert, wie Sie sich vor Angriffen mit Skriptexploits schützen können, bei denen versucht wird, bösartige Zeichen in eine Webseite einzufügen.|  
|[Grundlegende Sicherheitsmaßnahmen für Webanwendungen](https://docs.microsoft.com/previous-versions/aspnet/zdh19h94(v=vs.100))|Enthält allgemeine Sicherheitsinformationen und Links zu weiteren Erläuterungen.|  
  
## <a name="remoting"></a>Remoting  
 Mit .NET-Remoting können Sie auf einfache Weise weit verteilte Anwendungen erstellen, wobei sich die einzelnen Anwendungskomponenten auf demselben Computer oder weltweit an verschiedenen Standorten befinden können. Sie können Clientanwendungen erstellen, die Objekte in anderen Prozessen auf demselben Computer oder auf einem beliebigen anderen Computer im Netzwerk verwenden. Sie können .NET Remoting auch für die Kommunikation mit anderen Anwendungsdomänen im selben Prozess verwenden.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Konfiguration von Remoteanwendungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b8tysty8(v=vs.100))|Erläutert, wie Sie Remoting-Anwendungen so konfigurieren können, dass allgemeine Probleme vermieden werden.|  
|[Sicherheit beim Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/9hwst9th(v=vs.100))|Beschreibt die Authentifizierung und Verschlüsselung und enthält darüber hinaus weitere Sicherheitsthemen im Zusammenhang mit Remoting.|  
|[Remoting Überlegungen zu Sicherheit und](../../../../docs/framework/misc/security-and-remoting-considerations.md)|Beschreibt Sicherheitsprobleme mit geschützten Objekten und dem anwendungsdomänenübergreifenden Arbeiten.|  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Empfehlungen für Strategien für den Datenzugriff](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/8fxztkff(v=vs.90))
- [Sichern von Anwendungen](/visualstudio/ide/securing-applications)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
