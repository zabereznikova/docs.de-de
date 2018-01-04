---
title: "Informationen über Eingabehilfen für Steuerelemente in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b7c0d570dbb6389ef22dba635bbbc2885c5f3a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="0f1bc-102">Informationen über Eingabehilfen für Steuerelemente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0f1bc-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="0f1bc-103">Eingabehilfen sind spezielle Programme und Geräte, die es Personen mit Behinderungen ermöglichen, einen Computer effizienter zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="0f1bc-104">Beispiele hierfür sind Sprachausgaben für Blinde sowie Spracheingabe-Hilfsprogramme für Personen, die verbale Befehle geben, statt Maus oder Tastatur zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="0f1bc-105">Diese Eingabehilfen interagieren mit den Eingabehilfeeigenschaften, die von Windows Forms-Steuerelementen verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="0f1bc-106">Dies sind die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="0f1bc-106">These properties are:</span></span>  
  
-   <span data-ttu-id="0f1bc-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-107">**AccessibilityObject**</span></span>  
  
-   <span data-ttu-id="0f1bc-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-108">**AccessibleDefaultActionDescription**</span></span>  
  
-   <span data-ttu-id="0f1bc-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-109">**AccessibleDescription**</span></span>  
  
-   <span data-ttu-id="0f1bc-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-110">**AccessibleName**</span></span>  
  
-   <span data-ttu-id="0f1bc-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="0f1bc-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="0f1bc-112">AccessibilityObject-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0f1bc-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="0f1bc-113">Diese schreibgeschützte Eigenschaft enthält eine Instanz der <xref:System.Windows.Forms.AccessibleObject> .</span><span class="sxs-lookup"><span data-stu-id="0f1bc-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="0f1bc-114">Die **AccessibleObject** -Klasse implementiert die <xref:Accessibility.IAccessible> -Schnittstelle, die Informationen zur Beschreibung, zur Bildschirmposition, zu den Navigationsfähigkeiten und zum Wert des Steuerelements enthält.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="0f1bc-115">Der Entwickler legt diesen Wert fest, wenn das Steuerelement zum Formular hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="0f1bc-116">AccessibleDefaultActionDescription-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0f1bc-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="0f1bc-117">Diese Zeichenfolge beschreibt die Aktion des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-117">This string describes the action of the control.</span></span> <span data-ttu-id="0f1bc-118">Sie wird nicht im Eigenschaftenfenster angezeigt und kann nur in Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="0f1bc-119">Im folgenden Beispiel wird diese Eigenschaft für ein Schaltflächen-Steuerelement (Button) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-119">The following example sets this property for a button control:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
  
// C#  
Button1.AccessibleDefaultActionDescription =   
   "Closes the application.";  
  
// C++  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="0f1bc-120">Control.AccessibleDescription-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0f1bc-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="0f1bc-121">Diese Zeichenfolge beschreibt das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-121">This string describes the control.</span></span> <span data-ttu-id="0f1bc-122">Sie kann im Eigenschaftenfenster oder wie folgt in Code festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="0f1bc-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleDescription = "A button with text 'Exit'."  
  
// C#  
Button1.AccessibleDescription = "A button with text 'Exit'";  
  
// C++  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="0f1bc-123">Control.AccessibleName-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0f1bc-123">AccessibleName Property</span></span>  
 <span data-ttu-id="0f1bc-124">Diese Eigenschaft enthält den Namen des Steuerelements, der an Eingabehilfen gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="0f1bc-125">Sie kann im Eigenschaftenfenster oder wie folgt in Code festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="0f1bc-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
Button1.AccessibleName = "Order"  
  
// C#  
Button1.AccessibleName = "Order";  
  
// C++  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="0f1bc-126">AccessibleRole-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0f1bc-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="0f1bc-127">Diese Eigenschaft, die eine <xref:System.Windows.Forms.AccessibleRole> enthält, beschreibt die Rolle des Steuerelements in der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="0f1bc-128">Bei einem neuen Steuerelement ist die Eigenschaft auf `Default`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="0f1bc-129">Das heißt, dass sich ein **Schaltflächen** -Steuerelement standardmäßig wie eine **Schaltfläche**verhält.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="0f1bc-130">Sie können diese Eigenschaft auf einen anderen Wert festlegen, wenn das jeweilige Steuerelement eine andere Rolle hat.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="0f1bc-131">Beispielsweise könnte es sein, dass Sie ein **PictureBox** -Steuerelement als **Diagramm**verwenden und möchten, dass Eingabehilfen die Rolle als **Diagramm**, nicht als **PictureBox**melden.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="0f1bc-132">Es ist auch möglich, dass Sie diese Eigenschaft für benutzerdefinierte Steuerelemente angeben, die Sie entwickelt haben.</span><span class="sxs-lookup"><span data-stu-id="0f1bc-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="0f1bc-133">Diese Eigenschaft kann im Eigenschaftenfenster oder wie folgt in Code festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="0f1bc-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```  
' Visual Basic  
PictureBox1.AccessibleRole = AccessibleRole.Chart  
  
// C#  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
  
// C++  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f1bc-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f1bc-134">See Also</span></span>  
 <xref:System.Windows.Forms.AccessibleObject>  
 <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.AccessibleRole>
