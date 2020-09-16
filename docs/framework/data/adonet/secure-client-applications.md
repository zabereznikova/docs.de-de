---
title: Sichere Clientanwendungen
ms.date: 03/30/2017
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
ms.openlocfilehash: 8a946ab9b4cb75f7f890a01f0647f8a719c7bc03
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551542"
---
# <a name="secure-client-applications"></a>Sichere Clientanwendungen
Anwendungen bestehen in der Regel aus vielen Teilen, die alle so geschützt werden müssen, dass keine Daten verloren gehen oder das System nicht anderweitig gefährdet wird. Durch das Erstellen sicherer Benutzeroberflächen lassen sich viele Probleme vermeiden, weil Angreifer damit bereits blockiert werden, bevor sie überhaupt auf Daten oder Systemressourcen zugreifen können.  
  
## <a name="validate-user-input"></a>Validieren von Benutzereingaben  
 Beim Erstellen einer Anwendung mit Datenzugriff müssen Sie davon ausgehen, dass jede Benutzereingabe an sich schädlich sein kann, solange nichts Gegenteiliges bewiesen ist. Andernfalls gefährden Sie Ihre Anwendung. In .NET Framework gibt es Klassen, mit deren Hilfe Sie für Eingabesteuerelemente festlegen können, wie gültige Werte aussehen müssen. So können Sie z. B. festlegen, wie viele Buchstaben maximal eingegeben werden dürfen. Ereignishooks ermöglichen es Ihnen, Prozeduren zum Prüfen der Gültigkeit von Werten zu schreiben. Benutzereingabedaten können validiert und stark typisiert werden, sodass die Anwendung weniger anfällig für Skriptexploits und SQL Injection-Angriffe ist.  
  
> [!IMPORTANT]
> Zusätzlich muss die Benutzereingabe sowohl an der Datenquelle als auch in der Clientanwendung validiert werden, da Angreifer ansonsten Ihre Anwendung umgehen und die Datenquelle direkt angreifen könnten.  
  
 [Sicherheit und Benutzereingaben](../../../standard/security/security-and-user-input.md)  
 Beschreibt die Vorgehensweise bei kleinen und potenziell gefährlichen Fehlern im Zusammenhang mit der Benutzereingabe.  
  
 [Validieren von Benutzereingaben in ASP.net Web Pages](/previous-versions/aspnet/7kh55542(v=vs.100))  
 Enthält eine Übersicht über das Validieren der Benutzereingabe mit ASP.NET-Validierungssteuerelementen.  
  
 [Benutzereingaben in Windows Forms](/dotnet/desktop/winforms/user-input-in-windows-forms)  
 Enthält Links und Informationen zum Validieren von Eingaben mit Maus und Tastatur in einer Windows Forms-Anwendung.  
  
 [Reguläre Ausdrücke von .NET Framework](../../../standard/base-types/regular-expressions.md)  
 Beschreibt die Verwendung der <xref:System.Text.RegularExpressions.Regex>-Klasse, mit der die Gültigkeit der Benutzereingabe geprüft werden kann.  
  
## <a name="windows-applications"></a>Windows-Anwendungen  
 In der Vergangenheit wurden Windows-Anwendungen i. d. R. mit vollständigen Berechtigungen ausgeführt. .NET Framework stellt mit der Codezugriffssicherheit (Code Access Security, CAS) die Infrastruktur bereit, die erforderlich ist, um die Ausführung von Code in Windows-Anwendungen zu beschränken. CAS allein reicht aber zum Schutz Ihrer Anwendung nicht aus.  
  
 [Sicherheit in Windows Forms](/dotnet/desktop/winforms/windows-forms-security)  
 Erläutert das Sichern von Windows Forms-Anwendungen und stellt Links zu verwandten Themen bereit.  
  
 [Windows Forms und nicht verwaltete Anwendungen](/dotnet/desktop/winforms/advanced/windows-forms-and-unmanaged-applications)  
 Beschreibt die Interaktion mit nicht verwalteten Anwendungen in einer Windows Forms-Anwendung.  
  
 [ClickOnce-Bereitstellung für Windows Forms](/dotnet/desktop/winforms/clickonce-deployment-for-windows-forms)  
 Beschreibt die Verwendung einer `ClickOnce`-Bereitstellung in einer Windows Forms-Anwendung und erläutert die Auswirkungen auf die Sicherheit.  
  
## <a name="aspnet-and-xml-web-services"></a>ASP.NET und XML-Webdienste  
 ASP.NET-Anwendungen müssen im Allgemeinen den Zugriff auf einige Teile der Website einschränken und stellen andere Mechanismen für Datenschutz und die Sicherheit von Websites bereit. Über diese Links erhalten Sie nützliche Informationen zum Absichern Ihrer ASP.NET-Anwendung.  
  
 XML-Webdienste stellen Daten bereit, die von ASP.NET-Anwendungen, Windows Forms-Anwendungen oder anderen Webdiensten genutzt werden können. Um die Sicherheit des Webdiensts und die der Clientanwendung müssen Sie sich selbst kümmern.  
  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Resource|BESCHREIBUNG|  
|--------------|-----------------|  
|[Sichern von ASP.NET-Websites](/previous-versions/aspnet/91f66yxt(v=vs.100))|Erläutert das Sichern von ASP.NET-Anwendungen.|  
|[Sichern von mit ASP.NET erstellten XML-Webdiensten](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))|Veranschaulicht das Implementieren von Sicherheit für einen ASP.NET-Webdienst.|  
|[Übersicht über Skript Exploits](/previous-versions/aspnet/w1sw53ds(v=vs.100))|Erläutert, wie Sie sich vor Angriffen mit Skriptexploits schützen können, bei denen versucht wird, bösartige Zeichen in eine Webseite einzufügen.|  
|[Grundlegende Sicherheitsmaßnahmen für Webanwendungen](/previous-versions/aspnet/zdh19h94(v=vs.100))|Enthält allgemeine Sicherheitsinformationen und Links zu weiteren Erläuterungen.|  
  
## <a name="remoting"></a>Remoting  
 Mit .NET-Remoting können Sie auf einfache Weise weit verteilte Anwendungen erstellen, wobei sich die einzelnen Anwendungskomponenten auf demselben Computer oder weltweit an verschiedenen Standorten befinden können. Sie können Clientanwendungen erstellen, die Objekte in anderen Prozessen auf demselben Computer oder auf einem beliebigen anderen Computer im Netzwerk verwenden. Sie können .NET Remoting auch für die Kommunikation mit anderen Anwendungsdomänen im selben Prozess verwenden.  
  
|Ressource|BESCHREIBUNG|  
|--------------|-----------------|  
|[Konfiguration von Remote Anwendungen](/previous-versions/dotnet/netframework-4.0/b8tysty8(v=vs.100))|Erläutert, wie Sie Remoting-Anwendungen so konfigurieren können, dass allgemeine Probleme vermieden werden.|  
|[Sicherheit beim Remoting](/previous-versions/dotnet/netframework-4.0/9hwst9th(v=vs.100))|Beschreibt die Authentifizierung und Verschlüsselung und enthält darüber hinaus weitere Sicherheitsthemen im Zusammenhang mit Remoting.|  
|[Überlegungen zu Sicherheit und Remoting](../../misc/security-and-remoting-considerations.md)|Beschreibt Sicherheitsprobleme mit geschützten Objekten und dem anwendungsdomänenübergreifenden Arbeiten.|  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](securing-ado-net-applications.md)
- [Empfehlungen für Datenzugriffs Strategien](/previous-versions/visualstudio/visual-studio-2008/8fxztkff(v=vs.90))
- [Sichern von Anwendungen](/visualstudio/ide/securing-applications)
- [Schützen von Verbindungsinformationen](protecting-connection-information.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
