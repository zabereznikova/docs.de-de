---
title: Informationen über Eingabehilfen für Steuerelemente in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, accessibility
- controls [Windows Forms], accessibility
- accessibility [Windows Forms], Windows Forms controls
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 887dee6f-5059-4d57-957d-7c6fcd4acb10
ms.openlocfilehash: 672104db94826cfbe113a7ae0ea29546b0c3b9da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182001"
---
# <a name="providing-accessibility-information-for-controls-on-a-windows-form"></a><span data-ttu-id="3953c-102">Informationen über Eingabehilfen für Steuerelemente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3953c-102">Providing Accessibility Information for Controls on a Windows Form</span></span>
<span data-ttu-id="3953c-103">Eingabehilfen sind spezielle Programme und Geräte, die es Personen mit Behinderungen ermöglichen, einen Computer effizienter zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="3953c-103">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span> <span data-ttu-id="3953c-104">Beispiele hierfür sind Sprachausgaben für Blinde sowie Spracheingabe-Hilfsprogramme für Personen, die verbale Befehle geben, statt Maus oder Tastatur zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3953c-104">Examples include screen readers for people who are blind and voice input utilities for people who provide verbal commands instead of using the mouse or keyboard.</span></span> <span data-ttu-id="3953c-105">Diese Eingabehilfen interagieren mit den Eingabehilfeeigenschaften, die von Windows Forms-Steuerelementen verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="3953c-105">These accessibility aids interact with the accessibility properties exposed by Windows Forms controls.</span></span> <span data-ttu-id="3953c-106">Diese Eigenschaften sind:</span><span class="sxs-lookup"><span data-stu-id="3953c-106">These properties are:</span></span>  
  
- <span data-ttu-id="3953c-107">**AccessibilityObject**</span><span class="sxs-lookup"><span data-stu-id="3953c-107">**AccessibilityObject**</span></span>  
  
- <span data-ttu-id="3953c-108">**AccessibleDefaultActionDescription**</span><span class="sxs-lookup"><span data-stu-id="3953c-108">**AccessibleDefaultActionDescription**</span></span>  
  
- <span data-ttu-id="3953c-109">**AccessibleDescription**</span><span class="sxs-lookup"><span data-stu-id="3953c-109">**AccessibleDescription**</span></span>  
  
- <span data-ttu-id="3953c-110">**AccessibleName**</span><span class="sxs-lookup"><span data-stu-id="3953c-110">**AccessibleName**</span></span>  
  
- <span data-ttu-id="3953c-111">**AccessibleRole**</span><span class="sxs-lookup"><span data-stu-id="3953c-111">**AccessibleRole**</span></span>  
  
## <a name="accessibilityobject-property"></a><span data-ttu-id="3953c-112">AccessibilityObject-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3953c-112">AccessibilityObject Property</span></span>  
 <span data-ttu-id="3953c-113">Diese schreibgeschützte Eigenschaft enthält eine Instanz der <xref:System.Windows.Forms.AccessibleObject> .</span><span class="sxs-lookup"><span data-stu-id="3953c-113">This read-only property contains an <xref:System.Windows.Forms.AccessibleObject> instance.</span></span> <span data-ttu-id="3953c-114">Die **AccessibleObject** -Klasse implementiert die <xref:Accessibility.IAccessible> -Schnittstelle, die Informationen zur Beschreibung, zur Bildschirmposition, zu den Navigationsfähigkeiten und zum Wert des Steuerelements enthält.</span><span class="sxs-lookup"><span data-stu-id="3953c-114">The **AccessibleObject** implements the <xref:Accessibility.IAccessible> interface, which provides information about the control's description, screen location, navigational abilities, and value.</span></span> <span data-ttu-id="3953c-115">Der Entwickler legt diesen Wert fest, wenn das Steuerelement zum Formular hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3953c-115">The designer sets this value when the control is added to the form.</span></span>  
  
## <a name="accessibledefaultactiondescription-property"></a><span data-ttu-id="3953c-116">AccessibleDefaultActionDescription-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3953c-116">AccessibleDefaultActionDescription Property</span></span>  
 <span data-ttu-id="3953c-117">Diese Zeichenfolge beschreibt die Aktion des Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="3953c-117">This string describes the action of the control.</span></span> <span data-ttu-id="3953c-118">Sie wird nicht im Eigenschaftenfenster angezeigt und kann nur in Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3953c-118">It does not appear in the Properties window and may only be set in code.</span></span> <span data-ttu-id="3953c-119">Im folgenden Beispiel wird diese Eigenschaft für ein Schaltflächen-Steuerelement (Button) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3953c-119">The following example sets this property for a button control:</span></span>  
  
```vb  
Button1.AccessibleDefaultActionDescription = _  
   "Closes the application."  
```

```csharp  
Button1.AccessibleDefaultActionDescription =
   "Closes the application.";  
```

```cpp  
button1->AccessibleDefaultActionDescription =  
   "Closes the application.";  
```  
  
## <a name="accessibledescription-property"></a><span data-ttu-id="3953c-120">Control.AccessibleDescription-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3953c-120">AccessibleDescription Property</span></span>  
 <span data-ttu-id="3953c-121">Diese Zeichenfolge beschreibt das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3953c-121">This string describes the control.</span></span> <span data-ttu-id="3953c-122">Sie kann im Eigenschaftenfenster oder wie folgt in Code festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="3953c-122">It may be set in the Properties window, or in code as follows:</span></span>  
  
```vb  
Button1.AccessibleDescription = "A button with text 'Exit'."  
```

```csharp  
Button1.AccessibleDescription = "A button with text 'Exit'";  
```

```cpp  
button1->AccessibleDescription = "A button with text 'Exit'";  
```  
  
## <a name="accessiblename-property"></a><span data-ttu-id="3953c-123">Control.AccessibleName-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3953c-123">AccessibleName Property</span></span>  
 <span data-ttu-id="3953c-124">Diese Eigenschaft enthält den Namen des Steuerelements, der an Eingabehilfen gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="3953c-124">This is the name of a control reported to accessibility aids.</span></span> <span data-ttu-id="3953c-125">Sie kann im Eigenschaftenfenster oder wie folgt in Code festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="3953c-125">It may be set in the Properties window, or in code as follows:</span></span>  
  
```vb  
Button1.AccessibleName = "Order"  
```

```csharp  
Button1.AccessibleName = "Order";  
```

```cpp  
button1->AccessibleName = "Order";  
```  
  
## <a name="accessiblerole-property"></a><span data-ttu-id="3953c-126">AccessibleRole-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3953c-126">AccessibleRole Property</span></span>  
 <span data-ttu-id="3953c-127">Diese Eigenschaft, die eine <xref:System.Windows.Forms.AccessibleRole> enthält, beschreibt die Rolle des Steuerelements in der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="3953c-127">This property, which contains an <xref:System.Windows.Forms.AccessibleRole> enumeration, describes the user interface role of the control.</span></span> <span data-ttu-id="3953c-128">Bei einem neuen Steuerelement ist die Eigenschaft auf `Default` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3953c-128">A new control has the value set to `Default`.</span></span> <span data-ttu-id="3953c-129">Das heißt, dass sich ein **Schaltflächen** -Steuerelement standardmäßig wie eine **Schaltfläche**verhält.</span><span class="sxs-lookup"><span data-stu-id="3953c-129">This would mean that by default, a **Button** control acts as a **Button**.</span></span> <span data-ttu-id="3953c-130">Sie können diese Eigenschaft auf einen anderen Wert festlegen, wenn das jeweilige Steuerelement eine andere Rolle hat.</span><span class="sxs-lookup"><span data-stu-id="3953c-130">You may want to reset this property if a control has another role.</span></span> <span data-ttu-id="3953c-131">Beispielsweise könnte es sein, dass Sie ein **PictureBox** -Steuerelement als **Diagramm**verwenden und möchten, dass Eingabehilfen die Rolle als **Diagramm**, nicht als **PictureBox**melden.</span><span class="sxs-lookup"><span data-stu-id="3953c-131">For example, you may be using a **PictureBox** control as a **Chart**, and you may want accessibility aids to report the role as a **Chart**, not as a **PictureBox**.</span></span> <span data-ttu-id="3953c-132">Es ist auch möglich, dass Sie diese Eigenschaft für benutzerdefinierte Steuerelemente angeben, die Sie entwickelt haben.</span><span class="sxs-lookup"><span data-stu-id="3953c-132">You may also want to specify this property for custom controls you have developed.</span></span> <span data-ttu-id="3953c-133">Diese Eigenschaft kann im Eigenschaftenfenster oder wie folgt in Code festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="3953c-133">This property may be set in the Properties window, or in code as follows:</span></span>  
  
```vb
PictureBox1.AccessibleRole = AccessibleRole.Chart  
```

```csharp  
PictureBox1.AccessibleRole = AccessibleRole.Chart;  
```

```cpp  
pictureBox1->AccessibleRole = AccessibleRole::Chart;  
```  
  
## <a name="see-also"></a><span data-ttu-id="3953c-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3953c-134">See also</span></span>

- <xref:System.Windows.Forms.AccessibleObject>
- <xref:System.Windows.Forms.Control.AccessibilityObject%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDefaultActionDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleDescription%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleName%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.AccessibleRole%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.AccessibleRole>
