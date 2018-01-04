---
title: "Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f2c5a16ea1f07f7688c9df14bdb6b29350f3acf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="9f311-102">Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9f311-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="9f311-103">Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement umfasst leistungsstarke Layout-Funktionen, die Sie sorgfältig berücksichtigen sollten, bevor Sie in Windows Forms verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f311-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="9f311-104">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="9f311-104">Recommendations</span></span>  
 <span data-ttu-id="9f311-105">Die folgenden Empfehlungen können Sie verwenden die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement, um die besten davon profitieren.</span><span class="sxs-lookup"><span data-stu-id="9f311-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>  
  
### <a name="targeted-use"></a><span data-ttu-id="9f311-106">Zielgruppe</span><span class="sxs-lookup"><span data-stu-id="9f311-106">Targeted Use</span></span>  
 <span data-ttu-id="9f311-107">Verwenden der <xref:System.Windows.Forms.TableLayoutPanel> nur selten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="9f311-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="9f311-108">Sie sollten nicht in allen Situationen verwendet, die in der Größe veränderbaren Layout erfordern.</span><span class="sxs-lookup"><span data-stu-id="9f311-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="9f311-109">Die folgende Liste beschreibt Layouts, mit denen am meisten von der Verwendung von profitieren die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="9f311-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="9f311-110">Layouts, in denen es sind mehrere Teile des Formulars, die proportional zueinander zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="9f311-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>  
  
-   <span data-ttu-id="9f311-111">Layouts, mit die generiert dynamisch zur Laufzeit, z. B. Dateneingabeformulare, denen Benutzer anpassbare Felder hinzugefügt oder entfernt oder geändert werden, basierend auf Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9f311-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>  
  
-   <span data-ttu-id="9f311-112">Layouts, die an einem festen Gesamtgröße bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="9f311-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="9f311-113">Beispielsweise müssen unter Umständen einen (Dialogfeld), der kleiner als 800 x 600 bleiben soll, aber Sie lokalisierte Zeichenfolgen unterstützen müssen.</span><span class="sxs-lookup"><span data-stu-id="9f311-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>  
  
 <span data-ttu-id="9f311-114">Die folgende Liste beschreibt Layouts, mit denen nicht erheblich von der Verwendung gilt die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="9f311-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="9f311-115">Einfache Dateneingabeformulare mit einer einzelnen Spalte von Bezeichnungen und einer einzelnen Spalte Texteingabe Bereiche.</span><span class="sxs-lookup"><span data-stu-id="9f311-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>  
  
-   <span data-ttu-id="9f311-116">Formulare mit einem einzelnen großen anzeigen Bereich, der alle verfügbaren Platz ausfüllen soll, tritt eine Größe</span><span class="sxs-lookup"><span data-stu-id="9f311-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="9f311-117">Ein Beispiel hierfür ist ein Formular, das ein einzelnes zeigt <xref:System.Windows.Forms.PropertyGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9f311-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="9f311-118">In diesem Fall verwenden Sie verankern, da nichts erweitert werden soll, wenn die Größe des Formulars.</span><span class="sxs-lookup"><span data-stu-id="9f311-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>  
  
 <span data-ttu-id="9f311-119">Wählen Sie sorgfältig, welche Steuerelemente müssen in einem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9f311-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="9f311-120">Wenn Sie ausreichend Platz für den Text 30 % Verankerung vergrößert haben, können Sie verwenden die <xref:System.Windows.Forms.Control.Anchor%2A> nur-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9f311-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="9f311-121">Verwenden Sie das Layout erforderlichen Speicherplatzes nicht abschätzen können, <xref:System.Windows.Forms.Control.Dock%2A> und <xref:System.Windows.Forms.Control.Anchor%2A> ist einfacher als die Details des verbleibenden Speicherplatzes schätzen und <xref:System.Windows.Forms.Control.AutoSize%2A> Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9f311-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>  
  
 <span data-ttu-id="9f311-122">Im Allgemeinen gilt: beim Entwerfen des Layouts mit den <xref:System.Windows.Forms.TableLayoutPanel> steuern, den Entwurf so einfach wie möglich halten.</span><span class="sxs-lookup"><span data-stu-id="9f311-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>  
  
### <a name="use-the-document-outline-window"></a><span data-ttu-id="9f311-123">Verwenden Sie die Dokumentgliederung (Fenster)</span><span class="sxs-lookup"><span data-stu-id="9f311-123">Use the Document Outline Window</span></span>  
 <span data-ttu-id="9f311-124">Das Fenster "Dokumentgliederung" bietet Ihnen eine Strukturansicht der das Layout, die Sie verwenden können, um die Z-Reihenfolge und über-und untergeordneten Beziehungen zwischen Ihrer Steuerelemente zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="9f311-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="9f311-125">Aus der **Menü "Ansicht"**Option **Weitere Fenster**, und wählen Sie dann **Dokumentgliederung**.</span><span class="sxs-lookup"><span data-stu-id="9f311-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>  
  
### <a name="avoid-nesting"></a><span data-ttu-id="9f311-126">Vermeiden Sie die Schachtelung</span><span class="sxs-lookup"><span data-stu-id="9f311-126">Avoid Nesting</span></span>  
 <span data-ttu-id="9f311-127">Vermeiden Sie die Schachtelung andere <xref:System.Windows.Forms.TableLayoutPanel> steuert innerhalb einer <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9f311-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="9f311-128">Debuggen von verschachtelten Layouts kann schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="9f311-128">Debugging nested layouts can be difficult.</span></span>  
  
### <a name="avoid-visual-inheritance"></a><span data-ttu-id="9f311-129">Visuellen Vererbung vermeiden</span><span class="sxs-lookup"><span data-stu-id="9f311-129">Avoid Visual Inheritance</span></span>  
 <span data-ttu-id="9f311-130">Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement visuellen Vererbung in Windows Forms-Designer nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f311-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer.</span></span> <span data-ttu-id="9f311-131">Ein <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement in einer abgeleiteten Klasse wird angezeigt, da zur Entwurfszeit "gesperrt".</span><span class="sxs-lookup"><span data-stu-id="9f311-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f311-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f311-132">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
