---
title: "Gewusst wie: Bereitstellen von Hilfe in einer Windows-Anwendung | Microsoft Docs"
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
  - "Formulare, Bereitstellen von Hilfe"
  - "Hilfe, Windows-Anwendungen"
  - "HelpProvider-Komponente [Windows Forms]"
  - "HTML-Hilfe, Windows Forms"
  - "Windows-Anwendungen, Bereitstellen von Hilfe"
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Bereitstellen von Hilfe in einer Windows-Anwendung
Sie können die <xref:System.Windows.Forms.HelpProvider>\-Komponente verwenden, um Hilfethemen in einer Hilfedatei bestimmten Steuerelementen in Windows Forms zuzuordnen.  Die Hilfedatei kann entweder im Format HTML oder HTMLHelp 1.x oder höher vorliegen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So wird die Hilfe verfügbar  
  
1.  Ziehen Sie eine <xref:System.Windows.Forms.HelpProvider>\-Komponente aus der **Toolbox** in das Formular.  
  
     Die Komponente erscheint in der Taskleiste am unteren Rand des Windows Forms\-Designers.  
  
2.  Legen Sie die <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>\-Eigenschaft im **Eigenschaftenfenster** auf die CHM\-, COL\- oder HTM\-Hilfedatei fest.  
  
3.  Aktivieren Sie ein weiteres Steuerelement, das auf dem Formular erscheint, und legen Sie die [HelpKeyword](frlrfSystemWindowsFormsHelpProviderClassSetHelpKeywordTopic)\-Eigenschaft im **Eigenschaftenfenster** fest.  
  
     Dabei handelt es sich um die Zeichenfolge, die durch die <xref:System.Windows.Forms.HelpProvider>\-Komponente an die Hilfedatei übergeben wurde, um das entsprechende Hilfethema aufzurufen.  
  
4.  Legen Sie im **Eigenschaftenfenster** die [HelpNavigator](frlrfSystemWindowsFormsHelpProviderClassSetHelpNavigatorTopic)\-Eigenschaft auf einen Wert der <xref:System.Windows.Forms.HelpNavigator>\-Enumeration fest.  
  
     Dadurch wird festgelegt, wie die **HelpKeyword** \-Eigenschaft an das Hilfesystem übergeben wird.  In der folgenden Tabelle werden die möglichen Einstellungen und ihre Beschreibungen aufgeführt.  
  
    |Membername|Beschreibung|  
    |----------------|------------------|  
    |AssociateIndex|Gibt an, dass der Index für ein Thema in der angegebenen URL ausgeführt wurde.|  
    |Find|Gibt an, dass die Suchseite der angegebenen URL angezeigt wird.|  
    |Index|Gibt an, dass der Index der angegebenen URL angezeigt wird.|  
    |KeywordIndex|Gibt ein Schlüsselwort an, nach dem gesucht wird, und die Aktion, die in der angegebenen URL vorzunehmen ist.|  
    |TableOfContents|Gibt an, dass das Inhaltsverzeichnis der HTML 1.0\-Hilfedatei angezeigt wird.|  
    |Thema|Gibt an, dass das Thema angezeigt wird, auf das durch die angegebene URL verwiesen wird.|  
  
 Wenn Sie zur Laufzeit die Taste F1 drücken und das Steuerelement, für das Sie die **HelpKeyword**\-Eigenschaft und **HelpNavigator**\-Eigenschaft festgelegt haben, den Fokus hat, wird die Hilfedatei geöffnet, die Sie dieser <xref:System.Windows.Forms.HelpProvider>\-Komponente zugeordnet haben.  
  
 Momentan unterstützt die **HelpNamespace**\-Eigenschaft Hilfedateien in folgenden drei Formaten: HTMLHelp 1.x, HTMLHelp 2.0 und HTML.  Dies bedeutet, dass Sie die **HelpNamespace**\-Eigenschaft auf eine http:\/\/\-Adresse \(z. B. eine Web\-Seite\) festlegen können.  Daraufhin wird im Standardbrowser die Webseite mit der Zeichenfolge geöffnet, die in der als Anker verwendeten **HelpKeyword**\-Eigenschaft angegeben ist.  Der Anker wird verwendet, um zu einem bestimmten Teil einer HTML\-Seite zu springen.  
  
> [!IMPORTANT]
>  Überprüfen Sie alle von einem Client gesendeten Informationen sorgfältig, bevor Sie diese in der Anwendung verwenden.  Böswillige Benutzer könnten versuchen, ausführbare Skripts, SQL\-Anweisungen oder anderen Code zu senden oder einzufügen.  Bevor Sie die Eingabe eines Benutzers anzeigen, diese in einer Datenbank speichern oder damit arbeiten, müssen Sie sicherstellen, dass diese keine potenziell unsicheren Informationen enthält.  Ein sehr gebräuchlicher Weg zur Überprüfung der von einem Benutzer übermittelten Eingaben ist die Verwendung eines regulären Ausdrucks, um nach Schlüsselwörtern wie "SCRIPT" zu suchen.  
  
 Sie können die <xref:System.Windows.Forms.HelpProvider>\-Komponente zum Anzeigen der kontextbezogenen Hilfe auch dann verwenden, wenn Sie sie zum Anzeigen der Hilfedateien für die Steuerelemente auf Windows Forms konfiguriert haben.  Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen der kontextbezogenen Hilfe](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).  
  
## Siehe auch  
 [Gewusst wie: Anzeigen der kontextbezogenen Hilfe](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)   
 [Benutzerführung mithilfe von QuickInfos](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)   
 [Integrieren von Benutzerhilfe in Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)