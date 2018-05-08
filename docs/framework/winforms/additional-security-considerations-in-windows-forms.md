---
title: Weitere Überlegungen zur Sicherheit in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, secure calls to Windows API
- security [Windows Forms]
- security [Windows Forms], calling APIs
- Clipboard [Windows Forms], securing access
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
ms.openlocfilehash: a1d8606eb972a6e3bea52f6230cb893a4bbb5aac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="additional-security-considerations-in-windows-forms"></a>Weitere Überlegungen zur Sicherheit in Windows Forms
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]Sicherheitseinstellungen können möglicherweise dazu führen, dass Ihre Anwendung anders als in einer teilweise vertrauenswürdigen Umgebung als auf dem lokalen Computer ausgeführt wird. Der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] beschränkt den Zugriff auf wichtige lokale Ressourcen, beispielsweise unter anderem das Dateisystem, Netzwerk und nicht verwaltete APIs. Die Sicherheitseinstellungen haben Auswirkung auf die Möglichkeit zum Aufruf der Win32-API von Microsoft oder andere APIs, die nicht vom Sicherheitssystem überprüft werden können. Sicherheit wirkt sich auch auf andere Aspekte der Anwendung aus, einschließlich des Datei-und Datenzugriffs und des Druckens. Weitere Informationen zum Zugriff auf Dateien und Daten in einer teilweise vertrauenswürdigen Umgebung finden Sie unter [Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md). Weitere Informationen zum Drucken in einer teilweise vertrauenswürdigen Umgebung finden Sie unter [Mehr Sicherheit beim Drucken in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md).  
  
 In den folgenden Abschnitten wird das Arbeiten mit der Zwischenablage, das Bearbeiten von Fenstern und das Aufrufen der Win32-API über Anwendungen, die in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden, erläutert.  
  
## <a name="clipboard-access"></a>Zugriff auf die Zwischenablage  
 Die <xref:System.Security.Permissions.UIPermission> Klasse steuert den Zugriff auf die Zwischenablage, und die zugeordnete <xref:System.Security.Permissions.UIPermissionClipboard> Enumerationswert gibt die Zugriffsebene an. Die folgende Tabelle enthält die möglichen Berechtigungsebenen.  
  
|UIPermissionClipboard-Wert|Beschreibung|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard>|Die Zwischenablage kann ohne Einschränkung verwendet werden.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard>|Die Zwischenablage kann mit einigen Einschränkungen verwendet werden. Die Möglichkeit zum Einfügen von Daten in der Zwischenablage (Befehlsvorgang „Kopieren“ oder „Ausschneiden“) ist nicht eingeschränkt. Systeminterne Steuerelemente, die das Einfügen zulassen (z.B. von einem Textfeld), können Daten aus der Zwischenablage annehmen, Benutzersteuerelemente jedoch können nicht programmgesteuert aus der Zwischenablage gelesen werden.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.NoClipboard>|Die Zwischenablage kann nicht verwendet werden.|  
  
 Standardmäßig erhält die lokalen Intranetzone <xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard> Zugriff und der Internetzone empfängt <xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard> Zugriff. Dies bedeutet, dass die Anwendung zwar Daten in die Zwischenablage kopieren kann, sie kann jedoch keine Daten programmgesteuert in die Zwischenablage einfügen oder aus der Zwischenablage lesen. Diese Einschränkungen verhindern, dass Programme ohne volle Vertrauenswürdigkeit auf Inhalte, die von einer anderen Anwendung in die Zwischenablage kopiert wurden, gelesen werden können. Wenn Ihre Anwendung vollständigen Zugriff auf die Zwischenablage benötigt, aber Sie nicht über die Berechtigungen verfügen, müssen Sie die Berechtigungen für Ihre Anwendung erhöhen. Weitere Informationen zum Erhöhen von Berechtigungen finden Sie unter [Allgemeine Verwaltung der Sicherheitsrichtlinien](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## <a name="window-manipulation"></a>Fensterbearbeitung  
 Die <xref:System.Security.Permissions.UIPermission> -Klasse steuert auch die Berechtigung zum Ausführen von Fenstern und anderen UI-bezogene Aktionen sowie die zugehörigen <xref:System.Security.Permissions.UIPermissionWindow> Enumerationswert gibt die Zugriffsebene an. Die folgende Tabelle enthält die möglichen Berechtigungsebenen.  
  
 Standardmäßig erhält die lokalen Intranetzone <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> Zugriff und der Internetzone empfängt <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> Zugriff. Dies bedeutet, dass die Anwendung in der Internetzone die meisten Fenster- und Benutzeroberflächenaktionen ausführen kann, die Darstellung des Fensters jedoch wird geändert. Das geänderte Fenster zeigt bei Erstausführung eine Sprechblase an, enthält geänderten Titelleistentext und erfordert die Schaltfläche „Schließen“ in der Titelleiste. Die Sprechblase und die Titelleiste zeigen dem Benutzer der Anwendung an, dass die Anwendung mit teilweiser Vertrauenswürdigkeit ausgeführt wird.  
  
|UIPermissionWindow-Wert|Beschreibung|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>|Benutzer können alle Fenster und Benutzereingabeereignisse uneingeschränkt verwenden.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>|Benutzer können nur sicherere übergeordnete und sicherere untergeordnete Fenster zum Zeichnen verwenden, und sie können nur Benutzereingabeereignisse in diesen über- und untergeordneten Fenstern für die Benutzeroberfläche verwenden. Diese Safer sind deutlich gekennzeichnet und weisen minimale und maximale Größenbeschränkungen auf. Die Einschränkungen zu verhindern, dass potenziell schädliche Spoofingangriffe, z. B. imitating Anmeldebildschirme System oder auf dem Systemdesktop und programmgesteuerten Zugriff auf Windows, den Fokus-bezogene APIs und Verwendung von übergeordneten schränkt die <xref:System.Windows.Forms.ToolTip> Steuerelement|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>|Benutzer können nur sicherere untergeordnete Fenster zum Zeichnen verwenden, und sie können nur Benutzereingabeereignisse für die Benutzeroberfläche in diesem untergeordneten Fenster verwenden. Ein in einem Browser angezeigtes Steuerelement ist ein Beispiel für ein sichereres, untergeordnetes Fenster.|  
|<xref:System.Security.Permissions.UIPermissionWindow.NoWindows>|Benutzer können nicht willkürlich Fenster oder Benutzeroberflächenereignisse verwenden. Es kann keine Benutzeroberfläche verwendet werden.|  
  
 Jeder identifizierte Berechtigungsstufe der <xref:System.Security.Permissions.UIPermissionWindow> Enumeration ermöglicht weniger Aktionen als die Ebene. Die folgende Tabelle gibt an, die Aktionen, die nur durch eingeschränkt die <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> und <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> Werte. Die genauen Berechtigungen, die für jedes Mitglied erforderlich sind, finden Sie im Verweis für das Mitglied in der Dokumentation zur .NET Framework-Klassenbibliothek.  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> Berechtigung schränkt die in der folgenden Tabelle aufgeführten Aktionen an.  
  
|Komponente|Eingeschränkte Aktionen|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.Application>|– Festlegen der <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>-Eigenschaft.|  
|<xref:System.Windows.Forms.Control>|– Abrufen der <xref:System.Windows.Forms.Control.Parent%2A> Eigenschaft.<br />– Festlegen der `Region`-Eigenschaft.<br />-Aufrufen der <xref:System.Windows.Forms.Control.FindForm%2A> , <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> und <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A>, oder <xref:System.Windows.Forms.Control.SetTopLevel%2A> Methode.<br />-Aufrufen die <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> Methode, wenn die Steuerung zurückgegeben, ist kein untergeordneter des aufrufenden Steuerelements.<br />— Ändern des Steuerelementfokus innerhalb eines Containersteuerelements.|  
|<xref:System.Windows.Forms.Cursor>|– Festlegen der <xref:System.Windows.Forms.Cursor.Clip%2A>-Eigenschaft.<br />-Aufrufen die <xref:System.Windows.Forms.Control.Hide%2A> Methode.|  
|<xref:System.Windows.Forms.DataGrid>|-Aufrufen die <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A> Methode.|  
|<xref:System.Windows.Forms.Form>|– Abrufen der <xref:System.Windows.Forms.Form.ActiveForm%2A> oder <xref:System.Windows.Forms.Form.MdiParent%2A> Eigenschaft.<br />– Festlegen der <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A>, oder <xref:System.Windows.Forms.Form.TopMost%2A> Eigenschaft.<br />– Festlegen der <xref:System.Windows.Forms.Form.Opacity%2A> Eigenschaft unter 50 %.<br />– Festlegen der <xref:System.Windows.Forms.Form.WindowState%2A> Eigenschaft <xref:System.Windows.Forms.FormWindowState.Minimized> programmgesteuert.<br />-Aufrufen die <xref:System.Windows.Forms.Form.Activate%2A> Methode.<br />-Bei Verwendung der <xref:System.Windows.Forms.FormBorderStyle.None>, <xref:System.Windows.Forms.FormBorderStyle.FixedToolWindow>, und <xref:System.Windows.Forms.FormBorderStyle.SizableToolWindow> <xref:System.Windows.Forms.FormBorderStyle> Enumerationswerte.|  
|<xref:System.Windows.Forms.NotifyIcon>|-Bei Verwendung der <xref:System.Windows.Forms.NotifyIcon> Komponente wird vollständig beschränkt.|  
  
 Die <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> Wert bedeutet, dass zusätzlich zu den Einschränkungen von in der folgenden Tabelle aufgelisteten Aktionen der <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> Wert.  
  
|Komponente|Eingeschränkte Aktionen|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-Anzeigen eines Dialogfelds abgeleitet wurde. die <xref:System.Windows.Forms.CommonDialog> Klasse.|  
|<xref:System.Windows.Forms.Control>|-Aufrufen die <xref:System.Windows.Forms.Control.CreateGraphics%2A> Methode.<br />– Festlegen der <xref:System.Windows.Forms.Control.Cursor%2A>-Eigenschaft.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|– Festlegen der <xref:System.Windows.Forms.Cursor.Current%2A>-Eigenschaft.|  
|<xref:System.Windows.Forms.MessageBox>|-Aufrufen die <xref:System.Windows.Forms.Form.Show%2A> Methode.|  
  
### <a name="hosting-third-party-controls"></a>Hosten von Steuerelementen von Drittanbietern  
 Eine andere Art von Fensterbearbeitung kann auftreten, wenn in Ihren Formularen Steuerelemente von Drittanbietern gehostet werden. Ein Drittanbieter-Steuerelement ist eine beliebige benutzerdefinierte <xref:System.Windows.Forms.UserControl> , dass Sie nicht selbst entwickelt und kompiliert. Obwohl das Hostingszenario nur schwer nutzbar ist, kann das Steuerelement eines Drittanbieters theoretisch seine Renderingoberfläche über den gesamten Bereich Ihres Formulars erweitern. Dieses Steuerelement könnte dann ein wichtiges Dialogfeld imitieren und Informationen wie Kombinationen aus Benutzername und Kennwort oder Bankkontonummern von Benutzern anfordern.  
  
 Verwenden Sie zur Einschränkung dieses möglichen Risikos Steuerelemente von Drittanbietern nur von Anbietern, denen Sie vertrauen können. Wenn Sie Steuerelemente von Drittanbietern verwenden, die Sie von einer nicht überprüfbaren Quelle heruntergeladen haben, wird empfohlen, dass Sie den Quellcode auf mögliche Exploits überprüfen. Nachdem Sie sichergestellt haben, dass die Quelle nicht bösartig ist, sollten Sie die Assembly selbst kompilieren, um sicherzustellen, dass die Quelle der Assembly entspricht.  
  
## <a name="win32-api-calls"></a>Win32-API-Aufrufe  
 Wenn der Anwendungsentwurf das Aufrufen einer Funktion über die Win32-API erforderlich macht, greifen Sie auf nicht verwaltete Codes zu. In diesem Fall können die Aktionen des Codes für das Fenster oder das Betriebssystem nicht bestimmt werden, wenn Sie mit Win32-API-Aufrufen oder -Werten arbeiten. Die <xref:System.Security.Permissions.SecurityPermission> Klasse und die <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> Wert, der die <xref:System.Security.Permissions.SecurityPermissionFlag> Enumeration Steuern des Zugriffs auf nicht verwalteten Code. Eine Anwendung kann nicht verwalteten Code zugreifen, nur, wenn die Berechtigung erteilt wird die <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> Berechtigung. Standardmäßig können nur lokal ausgeführte Anwendungen den nicht verwalteten Code aufrufen.  
  
 Einige Windows Forms-Member angeben, nicht verwalteten Zugriff, erfordert die <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> Berechtigung. Die folgende Tabelle enthält die Elemente in der <xref:System.Windows.Forms> Namespace, der die Berechtigung erforderlich. Weitere Informationen zu den Berechtigungen, die für ein Member erforderlich sind, finden Sie in der Dokumentation zur .NET Framework-Klassenbibliothek.  
  
|Komponente|Member|  
|---------------|------------|  
|<xref:System.Windows.Forms.Application>|-   <xref:System.Windows.Forms.Application.AddMessageFilter%2A> Methode<br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A> Eigenschaft<br />-   `Exit` Methode<br />-   <xref:System.Windows.Forms.Application.ExitThread%2A> Methode<br />-   <xref:System.Windows.Forms.Application.ThreadException> Ereignis|  
|<xref:System.Windows.Forms.CommonDialog>|-   <xref:System.Windows.Forms.CommonDialog.HookProc%2A> Methode<br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\ Methode<br />-   <xref:System.Windows.Forms.CommonDialog.Reset%2A> Methode<br />-   <xref:System.Windows.Forms.CommonDialog.RunDialog%2A> Methode|  
|<xref:System.Windows.Forms.Control>|-   <xref:System.Windows.Forms.Control.CreateParams%2A> Methode<br />-   <xref:System.Windows.Forms.Control.DefWndProc%2A> Methode<br />-   <xref:System.Windows.Forms.Control.DestroyHandle%2A> Methode<br />-   <xref:System.Windows.Forms.Control.WndProc%2A> Methode|  
|<xref:System.Windows.Forms.Help>|-   <xref:System.Windows.Forms.Help.ShowHelp%2A> Methoden<br />-   <xref:System.Windows.Forms.Help.ShowHelpIndex%2A> Methode|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow> Klasse|  
|<xref:System.Windows.Forms.Screen>|-   <xref:System.Windows.Forms.Screen.FromHandle%2A> Methode|  
|<xref:System.Windows.Forms.SendKeys>|-   <xref:System.Windows.Forms.SendKeys.Send%2A> Methode<br />-   <xref:System.Windows.Forms.SendKeys.SendWait%2A> Methode|  
  
 Wenn Ihre Anwendung nicht über die Berechtigung zum Aufrufen von nicht verwalteten Codes verfügt, muss Ihre Anwendung anfordern <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> Berechtigung, oder Sie alternative Methoden zum Implementieren von Funktionen berücksichtigen; in vielen Fällen bietet Windows Forms eine verwaltete Alternative zu Win32-API Funktionen. Wenn keine Alternativen vorhanden sind und die Anwendung auf einen nicht verwalteten Code zugreifen muss, müssen Sie die Berechtigungen für die Anwendung erhöhen.  
  
 Mit der Berechtigung zum Aufrufen eines nicht verwalteten Codes kann eine Anwendung nahezu jede Aktion ausführen. Aus diesem Grund sollte die Berechtigung zum Aufrufen eines nicht verwalteten Codes nur für Anwendungen erteilt werden, die aus einer vertrauenswürdigen Quelle stammen. Alternativ, abhängig von der Anwendung, könnte der Teil der Anwendungsfunktionalität, über den der nicht verwaltete Code aufgerufen wird, optional sein oder nur in einer vollständig vertrauenswürdigen Umgebung aktiviert werden. Weitere Informationen zu problematischen Berechtigungen finden Sie unter [Problematische Berechtigungen und Richtlinienverwaltung](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md). Weitere Informationen zum Erhöhen von Berechtigungen finden Sie unter [NIB: Allgemeine Verwaltung der Sicherheitsrichtlinien](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## <a name="see-also"></a>Siehe auch  
 [Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [Mehr Sicherheit beim Drucken in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 [Übersicht über die Sicherheit in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [Sicherheit in Windows Forms](../../../docs/framework/winforms/windows-forms-security.md)  
 [Sichern von ClickOnce-Anwendungen](/visualstudio/deployment/securing-clickonce-applications)
