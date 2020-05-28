---
title: 'Vorgehensweise: Bereitstellen von Hilfe in einer Windows-Anwendung'
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
ms.openlocfilehash: 405de333ce936a864047e827e60f56a930059e26
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143606"
---
# <a name="how-to-provide-help-in-a-windows-application"></a>Vorgehensweise: Bereitstellen von Hilfe in einer Windows-Anwendung

Sie können die-Komponente verwenden <xref:System.Windows.Forms.HelpProvider> , um Hilfe Themen in einer Hilfedatei an bestimmte Steuerelemente auf Windows Forms anzufügen. Die Hilfedatei kann entweder im Format HTML oder HTMLHelp 1.x oder höher vorliegen.

## <a name="provide-help"></a>Bereitstellen von Hilfe

1. Ziehen Sie in Visual Studio aus der **Toolbox**eine <xref:System.Windows.Forms.HelpProvider> Komponente in das Formular.

     Die Komponente befindet sich anschließend auf der Taskleiste unten im Windows Forms-Designer.

2. Legen Sie im Fenster **Eigenschaften** die- <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> Eigenschaft auf die CHM-, Col-oder HTM-Hilfedatei fest.

3. Wählen Sie ein anderes Steuerelement auf dem Formular aus, und legen Sie im Fenster **Eigenschaften** die- <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> Eigenschaft fest.

     Dies ist die Zeichenfolge, die über die <xref:System.Windows.Forms.HelpProvider> Komponente an die Hilfedatei weitergeleitet wird, um das entsprechende Hilfethema einzuladen.

4. Legen Sie im Fenster **Eigenschaften** die- <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> Eigenschaft auf einen Wert der- <xref:System.Windows.Forms.HelpNavigator> Enumeration fest.

     Dies bestimmt die Art, wie die **HelpKeyword**-Eigenschaft an das Hilfesystem übergeben wird. In der folgenden Tabelle werden die möglichen Einstellungen und ihre Beschreibungen aufgeführt.

    |Elementname|BESCHREIBUNG|
    |-----------------|-----------------|
    |AssociateIndex|Gibt an, dass der Index für ein Thema in der angegebenen URL ausgeführt wurde.|
    |Suchen|Gibt an, dass die Suchseite der angegebenen URL angezeigt wird.|
    |Index|Gibt an, dass der Index der angegebenen URL angezeigt wird.|
    |KeywordIndex|Gibt ein Schlüsselwort an, nach dem gesucht wird, und die Aktion, die in der angegebenen URL vorzunehmen ist.|
    |TableOfContents|Gibt an, dass das Inhaltsverzeichnis der HTML 1.0-Hilfedatei angezeigt wird.|
    |Thema|Gibt an, dass das Thema angezeigt wird, auf das durch die angegebene URL verwiesen wird.|

 Drücken Sie zur Laufzeit F1, wenn das Steuerelement –, für das Sie die **HelpKeyword** -Eigenschaft und die **HelpNavigator** -Eigenschaft festgelegt haben – den Fokus hat, die Hilfedatei öffnet, die Sie mit dieser Komponente verknüpft haben <xref:System.Windows.Forms.HelpProvider> .

 Momentan unterstützt die **HelpNamespace**-Eigenschaft Hilfedateien in folgenden drei Formaten: HTMLHelp 1.x, HTMLHelp 2.0 und HTML. Daher können Sie die **HelpNamespace** -Eigenschaft auf eine `http://` Adresse (z. b. eine Webseite) festlegen. Daraufhin wird im Standardbrowser die Webseite mit der Zeichenfolge geöffnet, die in der als Anker verwendeten **HelpKeyword**-Eigenschaft angegeben ist. Der Anker wird verwendet, um zu einem bestimmten Teil einer HTML-Seite zu springen.

> [!IMPORTANT]
> Überprüfen Sie alle von einem Client gesendeten Informationen sorgfältig, bevor Sie diese in der Anwendung verwenden. Böswillige Benutzer könnten versuchen, ausführbare Skripts, SQL-Anweisungen oder anderen Code zu senden oder einzuschleusen. Bevor Sie die Eingabe eines Benutzers anzeigen, diese in einer Datenbank speichern oder damit arbeiten, müssen Sie sicherstellen, dass diese keine potenziell unsicheren Informationen enthält. Ein sehr gebräuchlicher Weg zur Überprüfung der von einem Benutzer übermittelten Eingaben ist die Verwendung eines regulären Ausdrucks, um nach Schlüsselwörtern wie SCRIPT zu suchen.

Sie können auch die- <xref:System.Windows.Forms.HelpProvider> Komponente verwenden, um die Popup Hilfe anzuzeigen, auch wenn Sie für die Anzeige von Hilfedateien für die Steuerelemente in Ihrer Windows Forms konfiguriert haben. Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen der kontextbezogenen Hilfe](how-to-display-pop-up-help.md).

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Anzeigen der kontextbezogenen Hilfe](how-to-display-pop-up-help.md)
- [Benutzerführung mithilfe von QuickInfos](control-help-using-tooltips.md)
- [Integrieren von Benutzerhilfe in Windows Forms](integrating-user-help-in-windows-forms.md)
- [Windows Forms](../index.md)
