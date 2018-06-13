---
title: Dialogfelder in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- dialog boxes [Windows Forms], Windows Forms
- Windows Forms dialog boxes
- dialogs [Windows Forms], using in Windows Forms
ms.assetid: d43d022b-451b-490d-9386-dc79d98fbf8a
ms.openlocfilehash: 302e59c607f179869bcf3923c3092e73a1eddc91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539902"
---
# <a name="dialog-boxes-in-windows-forms"></a><span data-ttu-id="5fa77-102">Dialogfelder in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5fa77-102">Dialog Boxes in Windows Forms</span></span>
<span data-ttu-id="5fa77-103">Dialogfelder werden für die Interaktion mit dem Benutzer und zum Abrufen von Informationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5fa77-103">Dialog boxes are used to interact with the user and retrieve information.</span></span> <span data-ttu-id="5fa77-104">Einfach ausgedrückt handelt es sich bei einem Dialogfeld um ein Formular mit einem eigenen <xref:System.Windows.Forms.FormBorderStyle>-Enumerationseigenschaftensatz, der auf `FixedDialog` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5fa77-104">In simple terms, a dialog box is a form with its <xref:System.Windows.Forms.FormBorderStyle> enumeration property set to `FixedDialog`.</span></span> <span data-ttu-id="5fa77-105">Sie können eigene benutzerdefinierte Dialogfelder mithilfe von Windows Forms-Designer in Visual Studio erstellen.</span><span class="sxs-lookup"><span data-stu-id="5fa77-105">You can construct your own custom dialog boxes by using the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="5fa77-106">Fügen Sie Steuerelemente wie `Label`, `Textbox` und `Button` hinzu, um die Dialogfelder an Ihre speziellen Anforderungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="5fa77-106">Add controls such as `Label`, `Textbox`, and `Button` to customize dialog boxes to your specific needs.</span></span> <span data-ttu-id="5fa77-107">Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] enthält ebenfalls vordefinierte Dialogfelder wie z. B. **Datei öffnen** und Meldungsfelder, die Sie für Ihre eigenen Anwendungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="5fa77-107">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also includes predefined dialog boxes, such as **File Open** and message boxes, which you can adapt for your own applications.</span></span> <span data-ttu-id="5fa77-108">Weitere Informationen finden Sie unter [Dialogfeld-Steuerelemente und-Komponenten](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5fa77-108">For more information, see [Dialog-Box Controls and Components](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5fa77-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5fa77-109">In This Section</span></span>  
 [<span data-ttu-id="5fa77-110">Gewusst wie: Anzeigen von Dialogfeldern für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5fa77-110">How to: Display Dialog Boxes for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-display-dialog-boxes-for-windows-forms.md)  
 <span data-ttu-id="5fa77-111">Enthält Anweisungen für das Anzeigen von Dialogfeldern.</span><span class="sxs-lookup"><span data-stu-id="5fa77-111">Gives directions for showing dialog boxes.</span></span>  
  
-   <span data-ttu-id="5fa77-112">[Vorgehensweise: Abrufen von Dialogfeldinformationen mithilfe mehrerer Eigenschaften](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5fa77-112">[How to: Retrieve Dialog Box Information Selectively Using Multiple Properties](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5fa77-113">[Vorgehensweise: Abrufen von Informationen aus dem übergeordneten Formular eines Dialogfelds](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5fa77-113">[How to: Retrieve Information from the Parent Form of a Dialog Box](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5fa77-114">[Benutzereingaben in Dialogfelder](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5fa77-114">[User Input to Dialog Boxes](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5fa77-115">[Vorgehensweise: Abrufen des Ergebnisses für Dialogfelder](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5fa77-115">[How to: Retrieve the Result for Dialog Boxes](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5fa77-116">[Exemplarische Vorgehensweise: Sammelabruf von Dialogfeldinformationen Dialogfeldinformationen mithilfe von Objekten](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5fa77-116">[Walkthrough: Retrieving Dialog Box Information Collectively Using Objects](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5fa77-117">[Vorgehensweise: Schließen von Dialogfeldern und Speichern von Benutzereingaben](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5fa77-117">[How to: Close Dialog Boxes and Retain User Input](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5fa77-118">[Vorgehensweise: Erstellen von Dialogfeldern zur Entwurfszeit](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5fa77-118">[How to: Create Dialog Boxes at Design Time](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="5fa77-119">[Vorgehensweise: Anzeigen von Meldungsfeldern](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="5fa77-119">[How to: Display Message Boxes](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5fa77-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="5fa77-120">Related Sections</span></span>  
 [<span data-ttu-id="5fa77-121">Dialogfeld-Steuerelemente und -Komponenten</span><span class="sxs-lookup"><span data-stu-id="5fa77-121">Dialog-Box Controls and Components</span></span>](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="5fa77-122">Listet die vordefinierten Dialogfeld-Steuerelemente auf.</span><span class="sxs-lookup"><span data-stu-id="5fa77-122">Lists the predefined dialog box controls.</span></span>  
  
 [<span data-ttu-id="5fa77-123">Ändern der Darstellung von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5fa77-123">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 <span data-ttu-id="5fa77-124">Enthält Links zu Themen, in denen beschrieben wird, wie die Darstellung von Windows Forms-Anwendungen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="5fa77-124">Contains links to topics that describe how to change the appearance of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="5fa77-125">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5fa77-125">TabControl Control Overview</span></span>](../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="5fa77-126">Erläutert, wie Sie ein TabControl-Steuerelement in ein Dialogfeld integrieren.</span><span class="sxs-lookup"><span data-stu-id="5fa77-126">Explains how you incorporate the tab control into a dialog box.</span></span>
