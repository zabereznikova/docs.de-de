---
title: Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement
ms.date: 03/30/2017
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
ms.openlocfilehash: 57abf3527af146f1ce918bcabbc6a5a34bfb9b34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222327"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="1296b-102">Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1296b-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="1296b-103">Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement bietet leistungsstarke Layout-Funktionen, die Sie sorgfältig berücksichtigen sollten, bevor Sie in Windows Forms verwenden.</span><span class="sxs-lookup"><span data-stu-id="1296b-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="1296b-104">Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="1296b-104">Recommendations</span></span>  
 <span data-ttu-id="1296b-105">Die folgenden Empfehlungen können Sie verwenden die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement seine optimal nutzen.</span><span class="sxs-lookup"><span data-stu-id="1296b-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>  
  
### <a name="targeted-use"></a><span data-ttu-id="1296b-106">Gezielte verwenden</span><span class="sxs-lookup"><span data-stu-id="1296b-106">Targeted Use</span></span>  
 <span data-ttu-id="1296b-107">Verwenden der <xref:System.Windows.Forms.TableLayoutPanel> nur selten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="1296b-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="1296b-108">Sie sollten nicht es in allen Situationen verwenden, die ein Layout mit veränderbarer Größe erfordern.</span><span class="sxs-lookup"><span data-stu-id="1296b-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="1296b-109">Die folgende Liste beschreibt die Layouts, mit denen am meisten von der Verwendung von profitieren die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="1296b-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="1296b-110">Layouts, in denen es sind mehrere Teile des Formulars, die proportional zueinander zu vergrößern.</span><span class="sxs-lookup"><span data-stu-id="1296b-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>  
  
-   <span data-ttu-id="1296b-111">Layouts, die dynamisch generiert, zur Laufzeit, wie z. B. Dateneingabeformularen, die anpassbaren Felder hinzugefügt oder entfernt oder geändert werden, basierend auf Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="1296b-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>  
  
-   <span data-ttu-id="1296b-112">Layouts, mit die auf eine gesamte feste Größe beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1296b-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="1296b-113">Z. B. möglicherweise ein Dialogfeld an, die kleiner als 800 x 600 beibehalten werden sollen, aber Sie lokalisierte Zeichenfolgen unterstützen müssen.</span><span class="sxs-lookup"><span data-stu-id="1296b-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>  
  
 <span data-ttu-id="1296b-114">Die folgende Liste beschreibt die Layouts, die von der Verwendung nicht besonders sinnvoll ist die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement:</span><span class="sxs-lookup"><span data-stu-id="1296b-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="1296b-115">Einfachen Dateneingabeformularen mit einer einzelnen Spalte von Bezeichnungen und einer einzelnen Spalte des Texteingabe Bereiche.</span><span class="sxs-lookup"><span data-stu-id="1296b-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>  
  
-   <span data-ttu-id="1296b-116">Formulare mit einem einzelnen großen anzeigen Bereich, der gesamte verfügbaren Platz ausfüllen soll, bei einer Größenänderung.</span><span class="sxs-lookup"><span data-stu-id="1296b-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="1296b-117">Ein Beispiel hierfür ist eine Form, die eine einzelne zeigt <xref:System.Windows.Forms.PropertyGrid> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1296b-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="1296b-118">In diesem Fall verwenden Sie verankern, da nichts erweitert werden soll, wenn die Größe des Formulars geändert wird.</span><span class="sxs-lookup"><span data-stu-id="1296b-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>  
  
 <span data-ttu-id="1296b-119">Wählen Sie sorgfältig, welche Steuerelemente müssen sich in einem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1296b-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="1296b-120">Wenn Sie über genügend Platz für den Text 30 % Verankerung Wachstum verfügen, sollten Sie verwenden die <xref:System.Windows.Forms.Control.Anchor%2A> nur-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1296b-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="1296b-121">Wenn Sie den Speicherplatz, der das Layout erforderliche einschätzen können, verwenden Sie <xref:System.Windows.Forms.Control.Dock%2A> und <xref:System.Windows.Forms.Control.Anchor%2A> ist einfacher als die Details des verbleibenden Speicherplatzes schätzen und <xref:System.Windows.Forms.Control.AutoSize%2A> Verhalten.</span><span class="sxs-lookup"><span data-stu-id="1296b-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>  
  
 <span data-ttu-id="1296b-122">Im Allgemeinen ist beim Entwerfen des Layouts mit den <xref:System.Windows.Forms.TableLayoutPanel> steuern, den Entwurf so einfach wie möglich zu halten.</span><span class="sxs-lookup"><span data-stu-id="1296b-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>  
  
### <a name="use-the-document-outline-window"></a><span data-ttu-id="1296b-123">Verwenden Sie die Dokumentgliederung (Fenster)</span><span class="sxs-lookup"><span data-stu-id="1296b-123">Use the Document Outline Window</span></span>  
 <span data-ttu-id="1296b-124">Das Fenster "Dokumentgliederung" bietet Ihnen eine Strukturansicht der das Layout, die Sie verwenden können, um die Z-Reihenfolge und über-und untergeordnete Beziehungen der Steuerelemente zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="1296b-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="1296b-125">Von der **Menü "Ansicht"** Option **Other Windows**, und wählen Sie dann **Dokumentgliederung**.</span><span class="sxs-lookup"><span data-stu-id="1296b-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>  
  
### <a name="avoid-nesting"></a><span data-ttu-id="1296b-126">Vermeiden Sie die Schachtelung</span><span class="sxs-lookup"><span data-stu-id="1296b-126">Avoid Nesting</span></span>  
 <span data-ttu-id="1296b-127">Vermeiden Sie andere Schachtelung <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelementen innerhalb einer <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1296b-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="1296b-128">Geschachtelte Layouts Debuggen kann schwierig sein.</span><span class="sxs-lookup"><span data-stu-id="1296b-128">Debugging nested layouts can be difficult.</span></span>  
  
### <a name="avoid-visual-inheritance"></a><span data-ttu-id="1296b-129">Visuellen Vererbung vermeiden</span><span class="sxs-lookup"><span data-stu-id="1296b-129">Avoid Visual Inheritance</span></span>  
 <span data-ttu-id="1296b-130">Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement visuellen Vererbung in der Windows Forms-Designer nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1296b-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer.</span></span> <span data-ttu-id="1296b-131">Ein <xref:System.Windows.Forms.TableLayoutPanel> als zur Entwurfszeit "gesperrt"-Steuerelement in einer abgeleiteten Klasse angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1296b-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1296b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1296b-132">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
