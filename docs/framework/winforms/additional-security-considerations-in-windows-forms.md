---
title: "Weitere &#220;berlegungen zur Sicherheit in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "API-Aufrufe, Windows Forms-Sicherheitseinstellungen"
  - "APIs, Aufrufen"
  - "Zwischenablage, Sichern des Zugriffs"
  - "Sicherheit [Windows Forms]"
  - "Sicherheit [Windows Forms], Aufrufen von APIs"
  - "Windows-API, Aufrufen"
  - "Windows-API, Sichere Aufrufe"
  - "Windows-API, Windows Forms-Sicherheitseinstellungen"
  - "Windows Forms, Sichere Aufrufe der Windows API"
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Weitere &#220;berlegungen zur Sicherheit in Windows&#160;Forms
Durch die Sicherheitseinstellungen von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] wird Ihre Anwendung in einer Umgebung mit teilweiser Vertrauenswürdigkeit möglicherweise anders ausgeführt als auf dem lokalen Computer.  Mit [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] wird der Zugriff auf wichtige lokale Ressourcen, beispielsweise das Dateisystem, das Netzwerk und nicht verwaltete APIs, beschränkt.  Die Sicherheitseinstellungen wirken sich auf die Aufrufmöglichkeiten der Microsoft Win32\-API oder anderer APIs aus, die vom Sicherheitssystem nicht identifiziert werden können.  Darüber hinaus werden weitere Aspekte der Anwendung beeinflusst, z. B. der Datei\- und Datenzugriff und das Drucken.  Weitere Informationen über Datei\- und Datenzugriff in einer Umgebung mit teilweiser Vertrauenswürdigkeit finden Sie unter [Mehr Sicherheit beim Datei\- und Datenzugriff in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md).  Weitere Informationen über das Drucken in einer Umgebung mit teilweiser Vertrauenswürdigkeit finden Sie unter [Mehr Sicherheit beim Drucken in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md).  
  
 In den folgenden Abschnitten wird das Arbeiten mit der Zwischenablage, das Bearbeiten von Fenstern und das Aufrufen der Win32\-API aus Anwendungen in einer Umgebung mit teilweiser Vertrauenswürdigkeit erläutert.  
  
## Zugriff auf die Zwischenablage  
 Die <xref:System.Security.Permissions.UIPermission>\-Klasse steuert den Zugriff auf die Zwischenablage. Der zugeordnete <xref:System.Security.Permissions.UIPermissionClipboard>\-Enumerationswert gibt die Zugriffsebene an.  In der folgenden Tabelle sind die möglichen Berechtigungsebenen aufgeführt.  
  
|UIPermissionClipboard\-Wert|Beschreibung|  
|---------------------------------|------------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|Die Zwischenablage kann ohne Einschränkungen verwendet werden.|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|Die Zwischenablage kann mit einigen Einschränkungen verwendet werden.  Das Ablegen von Daten in der Zwischenablage \(die Befehle zum Kopieren oder Ausschneiden\) ist uneingeschränkt möglich.  Systeminterne Steuerelemente wie Textfelder, bei denen das Einfügen möglich ist, können Daten aus der Zwischenablage entgegennehmen. Benutzersteuerelemente können jedoch nicht programmgesteuert aus der Zwischenablage lesen.|  
|<xref:System.Security.Permissions.UIPermissionClipboard>|Die Zwischenablage kann nicht verwendet werden.|  
  
 In der Standardeinstellung erhält die Zone Lokales Intranet Zugriff auf <xref:System.Security.Permissions.UIPermissionClipboard> und die Zone Internet Zugriff auf <xref:System.Security.Permissions.UIPermissionClipboard>.  Dies bedeutet, dass die Anwendung zwar Daten in die Zwischenablage kopieren, diese jedoch nicht programmgesteuert einfügen oder aus der Zwischenablage lesen kann.  Diese Einschränkungen sollen verhindern, dass nicht voll vertrauenswürdige Programme Inhalte lesen, die von anderen Anwendungen in die Zwischenablage kopiert wurden.  Wenn für die Anwendung der uneingeschränkte Zugriff auf die Zwischenablage erforderlich ist, Sie jedoch nicht über die entsprechenden Berechtigungen verfügen, müssen Sie die Berechtigungen für die Anwendung erhöhen.  Weitere Informationen zum Erhöhen von Berechtigungen finden Sie unter [Allgemeine Verwaltung der Sicherheitsrichtlinien](http://msdn.microsoft.com/de-de/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## Bearbeiten von Fenstern  
 Die <xref:System.Security.Permissions.UIPermission>\-Klasse steuert auch die Berechtigungen zum Ändern von Fenstern sowie für andere Aktionen auf der Benutzeroberfläche. Der verknüpfte <xref:System.Security.Permissions.UIPermissionWindow>\-Enumerationswert gibt die Zugriffsebene an.  In der folgenden Tabelle sind die möglichen Berechtigungsebenen aufgeführt.  
  
 In der Standardeinstellung erhält die Zone Lokales Intranet Zugriff auf <xref:System.Security.Permissions.UIPermissionWindow> und die Zone Internet Zugriff auf <xref:System.Security.Permissions.UIPermissionWindow>.  In der Internetzone können von der Anwendung somit die meisten Fenster\- und Benutzeroberflächenaktionen ausgeführt werden, die Darstellung des Fensters wird jedoch geändert.  Das geänderte Fenster zeigt beim ersten Ausführen einen Hinweis in einer Sprechblase an und enthält geänderten Titelleistentext. Außerdem ist auf der Titelleiste eine Schaltfläche zum Schließen erforderlich.  Durch die Sprechblase und in der Titelleiste wird dem Benutzer der Anwendung signalisiert, dass die Anwendung mit teilweiser Vertrauenswürdigkeit ausgeführt wird.  
  
|UIPermissionWindow\-Wert|Beschreibung|  
|------------------------------|------------------|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Benutzer können alle Fenster und Benutzereingabeereignisse ohne Einschränkung verwenden.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Die Benutzer können nur sicherere übergeordnete und untergeordnete Fenster zum Zeichnen verwenden. Außerdem können in diesen übergeordneten und untergeordneten Fenstern nur die Benutzereingabeereignisse der Benutzeroberfläche verwendet werden.  Diese sichereren Fenster sind eindeutig gekennzeichnet und weisen Beschränkungen hinsichtlich der minimalen und maximalen Größe auf.  Durch die Beschränkungen werden potenziell schädliche Spoofing\-Angriffe wie das Imitieren von Bildschirmen zur Systemanmeldung oder des Systemdesktops vermieden. Der programmgesteuerte Zugriff auf übergeordnete Fenster, fokusbezogene APIs und die Verwendung des <xref:System.Windows.Forms.ToolTip>\-Steuerelements werden eingeschränkt.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Die Benutzer können nur sicherere untergeordnete Fenster zum Zeichnen und nur Benutzereingabeereignisse für die Benutzeroberfläche in diesem untergeordneten Fenster verwenden.  Ein in einem Browser angezeigtes Steuerelement ist ein Beispiel für ein sichereres untergeordnetes Fenster.|  
|<xref:System.Security.Permissions.UIPermissionWindow>|Die Benutzer können keine Fenster oder Benutzeroberflächenereignisse verwenden.  Benutzeroberflächen können nicht verwendet werden.|  
  
 Jede Berechtigungsebene, die von der <xref:System.Security.Permissions.UIPermissionWindow>\-Enumeration angegeben wird, ermöglicht weniger Aktionen als die jeweils übergeordnete Berechtigungsebene.  In den folgenden Tabellen sind die Aktionen aufgelistet, die durch die Werte <xref:System.Security.Permissions.UIPermissionWindow> und <xref:System.Security.Permissions.UIPermissionWindow> beschränkt werden.  Die genauen Berechtigungen, die für die einzelnen Member erforderlich sind, finden Sie im Referenzthema des jeweiligen Members in der Dokumentation zur .NET Framework\-Klassenbibliothek.  
  
 Durch die <xref:System.Security.Permissions.UIPermissionWindow>\-Berechtigung werden die in der folgenden Tabelle aufgeführten Aktionen beschränkt:  
  
|Komponente|Eingeschränkte Aktionen|  
|----------------|-----------------------------|  
|<xref:System.Windows.Forms.Application>|-   Festlegen der <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A>\-Eigenschaft.|  
|<xref:System.Windows.Forms.Control>|-   Abrufen der <xref:System.Windows.Forms.Control.Parent%2A>\-Eigenschaft.<br />-   Festlegen der `Region`\-Eigenschaft.<br />-   Aufrufen von <xref:System.Windows.Forms.Control.FindForm%2A>, <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> und <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A> oder der <xref:System.Windows.Forms.Control.SetTopLevel%2A>\-Methode.<br />-   Aufrufen der <xref:System.Windows.Forms.Control.GetChildAtPoint%2A>\-Methode, wenn das zurückgegebene Steuerelement nicht dem aufrufenden Steuerelement untergeordnet ist.<br />-   Ändern des Steuerelementfokus innerhalb eines Containersteuerelements.|  
|<xref:System.Windows.Forms.Cursor>|-   Festlegen der <xref:System.Windows.Forms.Cursor.Clip%2A>\-Eigenschaft.<br />-   Aufrufen der <xref:System.Windows.Forms.Control.Hide%2A>\-Methode.|  
|<xref:System.Windows.Forms.DataGrid>|-   Aufrufen der <xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A>\-Methode.|  
|<xref:System.Windows.Forms.Form>|-   Abrufen der <xref:System.Windows.Forms.Form.ActiveForm%2A>\-Eigenschaft oder der <xref:System.Windows.Forms.Form.MdiParent%2A>\-Eigenschaft.<br />-   Festlegen der <xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A>\-Eigenschaft oder der<xref:System.Windows.Forms.Form.TopMost%2A>\-Eigenschaft.<br />-   Festlegen der <xref:System.Windows.Forms.Form.Opacity%2A>\-Eigenschaft auf einen Wert unter 50 %.<br />-   Programmgesteuertes Festlegen der <xref:System.Windows.Forms.Form.WindowState%2A>\-Eigenschaft auf <xref:System.Windows.Forms.FormWindowState>.<br />-   Aufrufen der <xref:System.Windows.Forms.Form.Activate%2A>\-Methode.<br />-   Verwenden der Enumerationswerte <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle> und <xref:System.Windows.Forms.FormBorderStyle>.|  
|<xref:System.Windows.Forms.NotifyIcon>|-   Die Verwendung der <xref:System.Windows.Forms.NotifyIcon>\-Komponente ist vollständig beschränkt.|  
  
 Zusätzlich zu den Einschränkungen durch den <xref:System.Security.Permissions.UIPermissionWindow>\-Wert werden durch den <xref:System.Security.Permissions.UIPermissionWindow>\-Wert die in der folgenden Tabelle aufgelisteten Aktionen beschränkt.  
  
|Komponente|Eingeschränkte Aktionen|  
|----------------|-----------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-   Anzeigen eines Dialogfelds, das von der <xref:System.Windows.Forms.CommonDialog>\-Klasse abgeleitet wurde.|  
|<xref:System.Windows.Forms.Control>|-   Aufrufen der <xref:System.Windows.Forms.Control.CreateGraphics%2A>\-Methode.<br />-   Festlegen der <xref:System.Windows.Forms.Control.Cursor%2A>\-Eigenschaft.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   Festlegen der <xref:System.Windows.Forms.Cursor.Current%2A>\-Eigenschaft.|  
|<xref:System.Windows.Forms.MessageBox>|-   Aufrufen der <xref:System.Windows.Forms.Form.Show%2A>\-Methode.|  
  
### Hosten von Drittanbietersteuerelementen  
 Eine weitere Art der Fenstermanipulation kann auftreten, wenn in Ihren Formularen Steuerelemente von Drittanbietern enthalten sind.  Jedes benutzerdefinierte <xref:System.Windows.Forms.UserControl>, das Sie nicht selbst entwickelt und kompiliert haben, ist ein Steuerelement eines Drittanbieters.  Obwohl in diesem Hostingszenario kaum auszunutzende Sicherheitslücken vorhanden sind, kann ein Steuerelement eines Drittanbieters seine Darstellungsoberfläche auf den gesamten Formularbereich erweitern.  Das Steuerelement kann dann ein wichtiges Dialogfeld imitieren, in dem Benutzer zur Eingabe Ihrer Benutzernamen und Kennwörter sowie Bankverbindungsdaten aufgefordert werden.  
  
 Verringern Sie dieses Risiko, indem Sie ausschließlich Steuerelemente von vertrauenswürdigen Anbietern verwenden.  Wenn Sie Steuerelemente von Drittanbietern aus nicht überprüfbaren Quellen herunterladen und verwenden, wird das Überprüfen des Quellcodes auf mögliche Sicherheitsrisiken empfohlen.  Wenn Sie sich vergewissert haben, dass es sich nicht um böswilligen Quellcode handelt, sollten Sie die Assembly selbst kompilieren, um sicherzustellen, dass der Quellcode mit der Assembly übereinstimmt.  
  
## Win32 API\-Aufrufe  
 Wenn für Ihren Anwendungsentwurf das Aufrufen einer Funktion aus der Win32\-API erforderlich ist, greifen Sie auf nicht verwalteten Code zu.  In diesem Fall können die Aktionen des Codes im Fenster oder im Betriebssystem bei der Arbeit mit Win32\-API\-Aufrufen und \-Werten nicht ermittelt werden.  Die <xref:System.Security.Permissions.SecurityPermission>\-Klasse und der <xref:System.Security.Permissions.SecurityPermissionFlag>\-Wert der <xref:System.Security.Permissions.SecurityPermissionFlag>\-Enumeration steuern den Zugriff auf nicht verwalteten Code.  Eine Anwendung kann nur auf nicht verwalteten Code zugreifen, wenn ihr die <xref:System.Security.Permissions.SecurityPermissionFlag>\-Berechtigung gewährt wurde.  In der Standardeinstellung kann nicht verwalteter Code nur von lokal ausgeführten Anwendungen aufgerufen werden.  
  
 Einige Windows Forms\-Member bieten nicht verwalteten Zugriff, der die <xref:System.Security.Permissions.SecurityPermissionFlag>\-Berechtigung erfordert.  In der folgenden Tabelle sind die Member im <xref:System.Windows.Forms>\-Namespace aufgelistet, für die diese Berechtigung erforderlich ist.  Weitere Informationen zu den für einen Member erforderlichen Berechtigungen finden Sie in der Dokumentation zur .NET Framework\-Klassenbibliothek.  
  
|Komponente|Member|  
|----------------|------------|  
|<xref:System.Windows.Forms.Application>|-   <xref:System.Windows.Forms.Application.AddMessageFilter%2A>\-Methode<br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A>\-Eigenschaft<br />-   `Exit`\-Methode<br />-   <xref:System.Windows.Forms.Application.ExitThread%2A>\-Methode<br />-   <xref:System.Windows.Forms.Application.ThreadException>\-Ereignis|  
|<xref:System.Windows.Forms.CommonDialog>|-   <xref:System.Windows.Forms.CommonDialog.HookProc%2A>\-Methode<br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\-Methode<br />-   <xref:System.Windows.Forms.CommonDialog.Reset%2A>\-Methode<br />-   <xref:System.Windows.Forms.CommonDialog.RunDialog%2A>\-Methode|  
|<xref:System.Windows.Forms.Control>|-   <xref:System.Windows.Forms.Control.CreateParams%2A>\-Methode<br />-   <xref:System.Windows.Forms.Control.DefWndProc%2A>\-Methode<br />-   <xref:System.Windows.Forms.Control.DestroyHandle%2A>\-Methode<br />-   <xref:System.Windows.Forms.Control.WndProc%2A>\-Methode|  
|<xref:System.Windows.Forms.Help>|-   <xref:System.Windows.Forms.Help.ShowHelp%2A>\-Methoden<br />-   <xref:System.Windows.Forms.Help.ShowHelpIndex%2A>\-Methode|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow>\-Klasse|  
|<xref:System.Windows.Forms.Screen>|-   <xref:System.Windows.Forms.Screen.FromHandle%2A>\-Methode|  
|<xref:System.Windows.Forms.SendKeys>|-   <xref:System.Windows.Forms.SendKeys.Send%2A>\-Methode<br />-   <xref:System.Windows.Forms.SendKeys.SendWait%2A>\-Methode|  
  
 Wenn Ihre Anwendung nicht zum Aufrufen von nicht verwaltetem Code berechtigt ist, muss von der Anwendung die <xref:System.Security.Permissions.SecurityPermissionFlag>\-Berechtigung angefordert werden, oder Sie müssen Features eventuell auf andere Weise implementieren. In vielen Fällen bietet Windows Forms eine verwaltete Alternative zu Win32\-API\-Funktionen.  Wenn es keine anderen Möglichkeiten gibt und die Anwendung auf nicht verwalteten Code zugreifen muss, müssen Sie die Berechtigungen für die Anwendung erhöhen.  
  
 Mit einer Berechtigung zum Aufrufen von nicht verwaltetem Code kann eine Anwendung nahezu jede Aktion ausführen.  Daher sollte eine solche Berechtigung nur Anwendungen gewährt werden, die aus einer vertrauenswürdigen Quelle stammen.  Je nach Anwendung können Sie den Teil der Anwendungsfunktionalität, der nicht verwalteten Code aufruft, auch optional gestalten oder nur in voll vertrauenswürdiger Umgebung aktivieren.  Weitere Informationen zu problematischen Berechtigungen finden Sie unter [Problematische Berechtigungen und Richtlinienverwaltung](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md).  Weitere Informationen zur Erhöhung von Berechtigungen finden Sie unter [NIB: General Security Policy Administration](http://msdn.microsoft.com/de-de/5121fe35-f0e3-402c-94ab-4f35b0a87b4b).  
  
## Siehe auch  
 [Mehr Sicherheit beim Datei\- und Datenzugriff in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)   
 [Mehr Sicherheit beim Drucken in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)   
 [Übersicht über die Sicherheit in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)   
 [Sicherheit in Windows Forms](../../../docs/framework/winforms/windows-forms-security.md)   
 [Sichern von ClickOnce\-Anwendungen](../Topic/Securing%20ClickOnce%20Applications.md)