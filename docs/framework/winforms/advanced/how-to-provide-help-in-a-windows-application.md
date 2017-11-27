---
title: 'Gewusst wie: Bereitstellen von Hilfe in einer Windows-Anwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows applications
- HTML Help [Windows Forms], Windows Forms
- Windows applications [Windows Forms], providing Help
- HelpProvider component [Windows Forms]
- forms [Windows Forms], providing Help
ms.assetid: 7c4e5cec-2bd2-4f0b-8d75-c2b88929bd61
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0f407f1c17c67ec99f4499b89c49932a4ba6d32c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-provide-help-in-a-windows-application"></a><span data-ttu-id="fbf45-102">Gewusst wie: Bereitstellen von Hilfe in einer Windows-Anwendung</span><span class="sxs-lookup"><span data-stu-id="fbf45-102">How to: Provide Help in a Windows Application</span></span>
<span data-ttu-id="fbf45-103">Können Sie von der <xref:System.Windows.Forms.HelpProvider> Komponente Hilfethemen in einer Hilfedatei bestimmten Steuerelementen in Windows Forms zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="fbf45-103">You can use of the <xref:System.Windows.Forms.HelpProvider> component to attach Help topics within a Help file to specific controls on Windows Forms.</span></span> <span data-ttu-id="fbf45-104">Die Hilfedatei kann entweder im Format HTML oder HTMLHelp 1.x oder höher vorliegen.</span><span class="sxs-lookup"><span data-stu-id="fbf45-104">The Help file can be either HTML or HTMLHelp 1.x or greater format.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbf45-105">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="fbf45-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fbf45-106">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fbf45-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fbf45-107">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="fbf45-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-provide-help"></a><span data-ttu-id="fbf45-108">So wird die Hilfe verfügbar</span><span class="sxs-lookup"><span data-stu-id="fbf45-108">To provide Help</span></span>  
  
1.  <span data-ttu-id="fbf45-109">Aus der **Toolbox**, ziehen Sie eine <xref:System.Windows.Forms.HelpProvider> -Komponente in Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="fbf45-109">From the **Toolbox**, drag a <xref:System.Windows.Forms.HelpProvider> component to your form.</span></span>  
  
     <span data-ttu-id="fbf45-110">Die Komponente befindet sich anschließend auf der Taskleiste unten im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="fbf45-110">The component will reside in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="fbf45-111">In der **Eigenschaften** legen die <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> -Eigenschaft auf die CHM, col- oder HTML-Hilfedatei.</span><span class="sxs-lookup"><span data-stu-id="fbf45-111">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property to the .chm, .col, or .htm Help file.</span></span>  
  
3.  <span data-ttu-id="fbf45-112">Wählen Sie ein anderes Steuerelement, Sie haben auf dem Formular, und in, der **Eigenschaften** legen die <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fbf45-112">Select another control you have on your form, and in the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> property.</span></span>  
  
     <span data-ttu-id="fbf45-113">Dies ist die Zeichenfolge, die durch Übergeben der <xref:System.Windows.Forms.HelpProvider> -Komponente in der Hilfedatei, die die entsprechenden Hilfethema aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="fbf45-113">This is the string passed through the <xref:System.Windows.Forms.HelpProvider> component to your Help file to summon the appropriate Help topic.</span></span>  
  
4.  <span data-ttu-id="fbf45-114">In der **Eigenschaften** legen die <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> Eigenschaft auf den Wert der <xref:System.Windows.Forms.HelpNavigator> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="fbf45-114">In the **Properties** window, set the <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> property to a value of the <xref:System.Windows.Forms.HelpNavigator> enumeration.</span></span>  
  
     <span data-ttu-id="fbf45-115">Dies bestimmt die Art, wie die **HelpKeyword**-Eigenschaft an das Hilfesystem übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="fbf45-115">This determines the way in which the **HelpKeyword** property is passed to the Help system.</span></span> <span data-ttu-id="fbf45-116">In der folgenden Tabelle werden die möglichen Einstellungen und ihre Beschreibungen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fbf45-116">The following table shows the possible settings and their descriptions.</span></span>  
  
    |<span data-ttu-id="fbf45-117">Membername</span><span class="sxs-lookup"><span data-stu-id="fbf45-117">Member Name</span></span>|<span data-ttu-id="fbf45-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbf45-118">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="fbf45-119">AssociateIndex</span><span class="sxs-lookup"><span data-stu-id="fbf45-119">AssociateIndex</span></span>|<span data-ttu-id="fbf45-120">Gibt an, dass der Index für ein Thema in der angegebenen URL ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="fbf45-120">Specifies that the index for a specified topic is performed in the specified URL.</span></span>|  
    |<span data-ttu-id="fbf45-121">Find</span><span class="sxs-lookup"><span data-stu-id="fbf45-121">Find</span></span>|<span data-ttu-id="fbf45-122">Gibt an, dass die Suchseite der angegebenen URL angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fbf45-122">Specifies that the search page of a specified URL is displayed.</span></span>|  
    |<span data-ttu-id="fbf45-123">Index</span><span class="sxs-lookup"><span data-stu-id="fbf45-123">Index</span></span>|<span data-ttu-id="fbf45-124">Gibt an, dass der Index der angegebenen URL angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fbf45-124">Specifies that the index of a specified URL is displayed.</span></span>|  
    |<span data-ttu-id="fbf45-125">KeywordIndex</span><span class="sxs-lookup"><span data-stu-id="fbf45-125">KeywordIndex</span></span>|<span data-ttu-id="fbf45-126">Gibt ein Schlüsselwort an, nach dem gesucht wird, und die Aktion, die in der angegebenen URL vorzunehmen ist.</span><span class="sxs-lookup"><span data-stu-id="fbf45-126">Specifies a keyword to search for and the action to take in the specified URL.</span></span>|  
    |<span data-ttu-id="fbf45-127">TableOfContents</span><span class="sxs-lookup"><span data-stu-id="fbf45-127">TableOfContents</span></span>|<span data-ttu-id="fbf45-128">Gibt an, dass das Inhaltsverzeichnis der HTML 1.0-Hilfedatei angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fbf45-128">Specifies that the table of contents of the HTML 1.0 Help file is displayed.</span></span>|  
    |<span data-ttu-id="fbf45-129">Topic</span><span class="sxs-lookup"><span data-stu-id="fbf45-129">Topic</span></span>|<span data-ttu-id="fbf45-130">Gibt an, dass das Thema angezeigt wird, auf das durch die angegebene URL verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="fbf45-130">Specifies that the topic referenced by the specified URL is displayed.</span></span>|  
  
 <span data-ttu-id="fbf45-131">Zur Laufzeit durch Drücken von F1 Wenn das Steuerelement – für die Sie festgelegt haben die **HelpKeyword** und **HelpNavigator** Eigenschaften – hat den Fokus öffnet die Hilfedatei, die Sie zugeordnet sind, <xref:System.Windows.Forms.HelpProvider> Komponente.</span><span class="sxs-lookup"><span data-stu-id="fbf45-131">At run time, pressing F1 when the control—for which you have set the **HelpKeyword** and **HelpNavigator** properties—has focus will open the Help file you associated with that <xref:System.Windows.Forms.HelpProvider> component.</span></span>  
  
 <span data-ttu-id="fbf45-132">Momentan unterstützt die **HelpNamespace**-Eigenschaft Hilfedateien in folgenden drei Formaten: HTMLHelp 1.x, HTMLHelp 2.0 und HTML.</span><span class="sxs-lookup"><span data-stu-id="fbf45-132">Currently, the **HelpNamespace** property supports Help files in the following three formats: HTMLHelp 1.x, HTMLHelp 2.0, and HTML.</span></span> <span data-ttu-id="fbf45-133">Dies bedeutet, dass Sie die **HelpNamespace**-Eigenschaft auf eine http://-Adresse (z. B. eine Webseite) festlegen können.</span><span class="sxs-lookup"><span data-stu-id="fbf45-133">Thus, you can set the **HelpNamespace** property to an http:// address, such as a Web page.</span></span> <span data-ttu-id="fbf45-134">Daraufhin wird im Standardbrowser die Webseite mit der Zeichenfolge geöffnet, die in der als Anker verwendeten **HelpKeyword**-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="fbf45-134">If this is done, it will open the default browser to the Web page with the string specified in the **HelpKeyword** property used as the anchor.</span></span> <span data-ttu-id="fbf45-135">Der Anker wird verwendet, um zu einem bestimmten Teil einer HTML-Seite zu springen.</span><span class="sxs-lookup"><span data-stu-id="fbf45-135">The anchor is used to jump to a specific part of an HTML page.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fbf45-136">Überprüfen Sie alle von einem Client gesendeten Informationen sorgfältig, bevor Sie diese in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="fbf45-136">Be careful to check any information that is sent from a client before using it in your application.</span></span> <span data-ttu-id="fbf45-137">Böswillige Benutzer könnten versuchen, ausführbare Skripts, SQL-Anweisungen oder anderen Code zu senden oder einzuschleusen.</span><span class="sxs-lookup"><span data-stu-id="fbf45-137">Malicious users might try to send or inject executable script, SQL statements, or other code.</span></span> <span data-ttu-id="fbf45-138">Bevor Sie die Eingabe eines Benutzers anzeigen, diese in einer Datenbank speichern oder damit arbeiten, müssen Sie sicherstellen, dass diese keine potenziell unsicheren Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="fbf45-138">Before you display a user's input, store it in a database, or work with it, check that it does not contain potentially unsafe information.</span></span> <span data-ttu-id="fbf45-139">Ein sehr gebräuchlicher Weg zur Überprüfung der von einem Benutzer übermittelten Eingaben ist die Verwendung eines regulären Ausdrucks, um nach Schlüsselwörtern wie SCRIPT zu suchen.</span><span class="sxs-lookup"><span data-stu-id="fbf45-139">A typical way to check is to use a regular expression to look for keywords such as "SCRIPT" when you receive input from a user.</span></span>  
  
 <span data-ttu-id="fbf45-140">Sie können auch die <xref:System.Windows.Forms.HelpProvider> Komponente zum Anzeigen der kontextbezogenen Hilfe, auch wenn Sie diese so konfiguriert, dass die Hilfedateien für die Steuerelemente in Windows Forms angezeigt haben.</span><span class="sxs-lookup"><span data-stu-id="fbf45-140">You can also use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help, even if you have it configured to display Help files for the controls on your Windows Forms.</span></span> <span data-ttu-id="fbf45-141">Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen der kontextbezogenen Hilfe](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span><span class="sxs-lookup"><span data-stu-id="fbf45-141">For more information, see [How to: Display Pop-up Help](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf45-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbf45-142">See Also</span></span>  
 [<span data-ttu-id="fbf45-143">Gewusst wie: Anzeigen der kontextbezogenen Hilfe</span><span class="sxs-lookup"><span data-stu-id="fbf45-143">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 [<span data-ttu-id="fbf45-144">Benutzerführung mithilfe von QuickInfos</span><span class="sxs-lookup"><span data-stu-id="fbf45-144">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [<span data-ttu-id="fbf45-145">Integrieren von Benutzerhilfe in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fbf45-145">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="fbf45-146">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fbf45-146">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
