---
title: Dialogfelder in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- dialog boxes [Windows Forms], Windows Forms
- Windows Forms dialog boxes
- dialogs [Windows Forms], using in Windows Forms
ms.assetid: d43d022b-451b-490d-9386-dc79d98fbf8a
ms.openlocfilehash: ef07c087ca43efaf99231453fcb56af0db24234a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387740"
---
# <a name="dialog-boxes-in-windows-forms"></a><span data-ttu-id="1903a-102">Dialogfelder in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1903a-102">Dialog Boxes in Windows Forms</span></span>
<span data-ttu-id="1903a-103">Dialogfelder werden für die Interaktion mit dem Benutzer und zum Abrufen von Informationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1903a-103">Dialog boxes are used to interact with the user and retrieve information.</span></span> <span data-ttu-id="1903a-104">Einfach ausgedrückt handelt es sich bei einem Dialogfeld um ein Formular mit einem eigenen <xref:System.Windows.Forms.FormBorderStyle>-Enumerationseigenschaftensatz, der auf `FixedDialog` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1903a-104">In simple terms, a dialog box is a form with its <xref:System.Windows.Forms.FormBorderStyle> enumeration property set to `FixedDialog`.</span></span> <span data-ttu-id="1903a-105">Sie können eigene benutzerdefinierte Dialogfelder erstellen, indem Sie mit der Windows Forms-Designer in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1903a-105">You can construct your own custom dialog boxes by using the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="1903a-106">Fügen Sie Steuerelemente wie `Label`, `Textbox` und `Button` hinzu, um die Dialogfelder an Ihre speziellen Anforderungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="1903a-106">Add controls such as `Label`, `Textbox`, and `Button` to customize dialog boxes to your specific needs.</span></span> <span data-ttu-id="1903a-107">Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] enthält ebenfalls vordefinierte Dialogfelder wie z. B. **Datei öffnen** und Meldungsfelder, die Sie für Ihre eigenen Anwendungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="1903a-107">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also includes predefined dialog boxes, such as **File Open** and message boxes, which you can adapt for your own applications.</span></span> <span data-ttu-id="1903a-108">Weitere Informationen finden Sie unter [Dialogfeld-Steuerelemente und-Komponenten](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1903a-108">For more information, see [Dialog-Box Controls and Components](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1903a-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1903a-109">In This Section</span></span>  
 [<span data-ttu-id="1903a-110">Gewusst wie: Anzeigen von Dialogfeldern für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1903a-110">How to: Display Dialog Boxes for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-display-dialog-boxes-for-windows-forms.md)  
 <span data-ttu-id="1903a-111">Enthält Anweisungen für das Anzeigen von Dialogfeldern.</span><span class="sxs-lookup"><span data-stu-id="1903a-111">Gives directions for showing dialog boxes.</span></span>  
  
-   <span data-ttu-id="1903a-112">[Vorgehensweise: Abrufen von Dialogfeldinformationen mithilfe mehrerer Eigenschaften](https://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1903a-112">[How to: Retrieve Dialog Box Information Selectively Using Multiple Properties](https://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="1903a-113">[Vorgehensweise: Abrufen von Informationen aus dem übergeordneten Formular eines Dialogfelds](https://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1903a-113">[How to: Retrieve Information from the Parent Form of a Dialog Box](https://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="1903a-114">[Benutzereingaben in Dialogfelder](https://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1903a-114">[User Input to Dialog Boxes](https://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="1903a-115">[Vorgehensweise: Abrufen des Ergebnisses für Dialogfelder](https://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1903a-115">[How to: Retrieve the Result for Dialog Boxes](https://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="1903a-116">[Exemplarische Vorgehensweise: Sammelabruf von Dialogfeldinformationen mithilfe von Objekten](https://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1903a-116">[Walkthrough: Retrieving Dialog Box Information Collectively Using Objects](https://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="1903a-117">[Vorgehensweise: Schließen von Dialogfeldern und Speichern von Benutzereingaben](https://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1903a-117">[How to: Close Dialog Boxes and Retain User Input](https://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="1903a-118">[Vorgehensweise: Erstellen von Dialogfeldern zur Entwurfszeit](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1903a-118">[How to: Create Dialog Boxes at Design Time](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="1903a-119">[Vorgehensweise: Anzeigen von Meldungsfeldern](https://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="1903a-119">[How to: Display Message Boxes](https://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1903a-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1903a-120">Related Sections</span></span>  
 [<span data-ttu-id="1903a-121">Dialogfeld-Steuerelemente und -Komponenten</span><span class="sxs-lookup"><span data-stu-id="1903a-121">Dialog-Box Controls and Components</span></span>](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="1903a-122">Listet die vordefinierten Dialogfeld-Steuerelemente auf.</span><span class="sxs-lookup"><span data-stu-id="1903a-122">Lists the predefined dialog box controls.</span></span>  
  
 [<span data-ttu-id="1903a-123">Ändern der Darstellung von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1903a-123">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 <span data-ttu-id="1903a-124">Enthält Links zu Themen, in denen beschrieben wird, wie die Darstellung von Windows Forms-Anwendungen geändert wird.</span><span class="sxs-lookup"><span data-stu-id="1903a-124">Contains links to topics that describe how to change the appearance of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="1903a-125">Übersicht über das TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1903a-125">TabControl Control Overview</span></span>](../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="1903a-126">Erläutert, wie Sie ein TabControl-Steuerelement in ein Dialogfeld integrieren.</span><span class="sxs-lookup"><span data-stu-id="1903a-126">Explains how you incorporate the tab control into a dialog box.</span></span>
