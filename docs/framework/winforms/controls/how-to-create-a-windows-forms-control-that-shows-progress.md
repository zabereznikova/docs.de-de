---
title: Create Control, das den Fortschritt anzeigt
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
ms.openlocfilehash: 9d2cf353ba2309380221bb51733baaca1b81a5d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731177"
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a><span data-ttu-id="efec1-102">Gewusst wie: Erstellen eines Windows Forms-Steuerelements, das den Fortschritt anzeigt</span><span class="sxs-lookup"><span data-stu-id="efec1-102">How to: Create a Windows Forms Control That Shows Progress</span></span>
<span data-ttu-id="efec1-103">Das folgende Codebeispiel zeigt ein benutzerdefiniertes Steuerelement mit dem Namen `FlashTrackBar`, mit dem der Benutzer die Ebene oder den Fortschritt einer Anwendung anzeigen lassen kann.</span><span class="sxs-lookup"><span data-stu-id="efec1-103">The following code example shows a custom control called `FlashTrackBar` that can be used to show the user the level or the progress of an application.</span></span> <span data-ttu-id="efec1-104">Es verwendet Farbverläufe, um den Fortschritt darzustellen.</span><span class="sxs-lookup"><span data-stu-id="efec1-104">It uses a gradient to visually represent progress.</span></span>  
  
 <span data-ttu-id="efec1-105">Das `FlashTrackBar`-Steuerelement stellt die folgenden Konzepte dar:</span><span class="sxs-lookup"><span data-stu-id="efec1-105">The `FlashTrackBar` control illustrates the following concepts:</span></span>  
  
- <span data-ttu-id="efec1-106">Speichern benutzerdefinierter Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="efec1-106">Defining custom properties.</span></span>  
  
- <span data-ttu-id="efec1-107">Definieren benutzerdefinierter Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="efec1-107">Defining custom events.</span></span> <span data-ttu-id="efec1-108">(`FlashTrackBar` definiert das `ValueChanged`-Ereignis.)</span><span class="sxs-lookup"><span data-stu-id="efec1-108">(`FlashTrackBar` defines the `ValueChanged` event.)</span></span>  
  
- <span data-ttu-id="efec1-109">Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode, um Logik zum Zeichnen des Steuer Elements bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="efec1-109">Overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method to provide logic to draw the control.</span></span>  
  
- <span data-ttu-id="efec1-110">Berechnen des Bereichs, der zum Zeichnen des Steuer Elements mithilfe der <xref:System.Windows.Forms.Control.ClientRectangle%2A>-Eigenschaft verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="efec1-110">Computing the area available for drawing the control by using its <xref:System.Windows.Forms.Control.ClientRectangle%2A> property.</span></span> <span data-ttu-id="efec1-111">Dies erfolgt normalerweise durch `FlashTrackBar` in der Methode `OptimizedInvalidate`.</span><span class="sxs-lookup"><span data-stu-id="efec1-111">`FlashTrackBar` does this in its `OptimizedInvalidate` method.</span></span>  
  
- <span data-ttu-id="efec1-112">Implementieren der Serialisierung oder Dauerhaftigkeit für eine Eigenschaft, wenn sie in Windows Forms-Designer geändert wird.</span><span class="sxs-lookup"><span data-stu-id="efec1-112">Implementing serialization or persistence for a property when it is changed in the Windows Forms Designer.</span></span> <span data-ttu-id="efec1-113">`FlashTrackBar` definiert die Methoden `ShouldSerializeStartColor` und `ShouldSerializeEndColor` für die Serialisierung der Eigenschaften `StartColor` und `EndColor`.</span><span class="sxs-lookup"><span data-stu-id="efec1-113">`FlashTrackBar` defines the `ShouldSerializeStartColor` and `ShouldSerializeEndColor` methods for serializing its `StartColor` and `EndColor` properties.</span></span>  
  
 <span data-ttu-id="efec1-114">In der folgenden Tabelle werden die von `FlashTrackBar` benutzerdefinierten Eigenschaften dargestellt.</span><span class="sxs-lookup"><span data-stu-id="efec1-114">The following table shows the custom properties defined by `FlashTrackBar`.</span></span>  
  
|<span data-ttu-id="efec1-115">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="efec1-115">Property</span></span>|<span data-ttu-id="efec1-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="efec1-116">Description</span></span>|  
|--------------|-----------------|  
|`AllowUserEdit`|<span data-ttu-id="efec1-117">Gibt an, ob der Benutzer den Wert der Flash-Trackleiste durch Klicken und Ziehen verändern kann.</span><span class="sxs-lookup"><span data-stu-id="efec1-117">Indicates whether the user can change the value of the flash track bar by clicking and dragging it.</span></span>|  
|`EndColor`|<span data-ttu-id="efec1-118">Gibt die Farbe am Ende der Trackleiste an.</span><span class="sxs-lookup"><span data-stu-id="efec1-118">Specifies the ending color of the track bar.</span></span>|  
|`DarkenBy`|<span data-ttu-id="efec1-119">Gibt an, wie viel dunkler der Hintergrund in Bezug auf den Farbverlauf des Vordergrunds angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="efec1-119">Specifies how much to darken the background with respect to the foreground gradient.</span></span>|  
|`Max`|<span data-ttu-id="efec1-120">Gibt den maximalen Wert der Trackleiste an.</span><span class="sxs-lookup"><span data-stu-id="efec1-120">Specifies the maximum value of the track bar.</span></span>|  
|`Min`|<span data-ttu-id="efec1-121">Gibt den minimalen Wert der Trackleiste an.</span><span class="sxs-lookup"><span data-stu-id="efec1-121">Specifies the minimum value of the track bar.</span></span>|  
|`StartColor`|<span data-ttu-id="efec1-122">Gibt die verwendete Anfangsfarbe des Farbverlaufs an.</span><span class="sxs-lookup"><span data-stu-id="efec1-122">Specifies the starting color of the gradient.</span></span>|  
|`ShowPercentage`|<span data-ttu-id="efec1-123">Gibt an, ob über dem Farbverlauf ein Prozentsatz angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="efec1-123">Indicates whether to display a percentage over the gradient.</span></span>|  
|`ShowValue`|<span data-ttu-id="efec1-124">Gibt an, ob über dem Farbverlauf der aktuelle Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="efec1-124">Indicates whether to display the current value over the gradient.</span></span>|  
|`ShowGradient`|<span data-ttu-id="efec1-125">Gibt an, ob die Trackleiste einen Farbverlauf mit dem aktuellen Wert anzeigen soll.</span><span class="sxs-lookup"><span data-stu-id="efec1-125">Indicates whether the track bar should display a color gradient showing the current value.</span></span>|  
|-   `Value`|<span data-ttu-id="efec1-126">Gibt den aktuellen Wert der Trackleiste an.</span><span class="sxs-lookup"><span data-stu-id="efec1-126">Specifies the current value of the track bar.</span></span>|  
  
 <span data-ttu-id="efec1-127">In der folgenden Tabelle werden zusätzliche von `FlashTrackBar:` definierte Member gezeigt: das durch eine geänderte Eigenschaft ausgelöste Ereignis und die Methode, die das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="efec1-127">The following table shows additional members defined by `FlashTrackBar:` the property-changed event and the method that raises the event.</span></span>  
  
|<span data-ttu-id="efec1-128">Member</span><span class="sxs-lookup"><span data-stu-id="efec1-128">Member</span></span>|<span data-ttu-id="efec1-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="efec1-129">Description</span></span>|  
|------------|-----------------|  
|`ValueChanged`|<span data-ttu-id="efec1-130">Das Ereignis, das ausgelöst wird, wenn die Eigenschaft `Value` der Trackleiste verändert wird.</span><span class="sxs-lookup"><span data-stu-id="efec1-130">The event that is raised when the `Value` property of the track bar changes.</span></span>|  
|`OnValueChanged`|<span data-ttu-id="efec1-131">Die Methode, die das `ValueChanged`-Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="efec1-131">The method that raises the `ValueChanged` event.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="efec1-132">`FlashTrackBar` verwendet die <xref:System.EventArgs>-Klasse für Ereignisdaten und <xref:System.EventHandler> für den Ereignis Delegaten.</span><span class="sxs-lookup"><span data-stu-id="efec1-132">`FlashTrackBar` uses the <xref:System.EventArgs> class for event data and <xref:System.EventHandler> for the event delegate.</span></span>  
  
 <span data-ttu-id="efec1-133">Um die entsprechenden *EventName* -Ereignisse zu behandeln, überschreibt `FlashTrackBar` die folgenden Methoden, die von <xref:System.Windows.Forms.Control?displayProperty=nameWithType>geerbt werden:</span><span class="sxs-lookup"><span data-stu-id="efec1-133">To handle the corresponding *EventName* events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
- <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 <span data-ttu-id="efec1-134">Um die entsprechenden Eigenschaften geänderten Ereignisse zu behandeln, überschreibt `FlashTrackBar` die folgenden Methoden, die es von <xref:System.Windows.Forms.Control?displayProperty=nameWithType>erbt:</span><span class="sxs-lookup"><span data-stu-id="efec1-134">To handle the corresponding property-changed events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a><span data-ttu-id="efec1-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="efec1-135">Example</span></span>  
 <span data-ttu-id="efec1-136">Das `FlashTrackBar`-Steuerelement definiert zwei UI-Typ-Editoren, `FlashTrackBarValueEditor` und `FlashTrackBarDarkenByEditor`, die in den folgenden Codeauflistungen veranschaulicht werden.</span><span class="sxs-lookup"><span data-stu-id="efec1-136">The `FlashTrackBar` control defines two UI type editors, `FlashTrackBarValueEditor` and `FlashTrackBarDarkenByEditor`, which are shown in the following code listings.</span></span> <span data-ttu-id="efec1-137">Die `HostApp` -Klasse verwendet das `FlashTrackBar`-Steuerelement in einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="efec1-137">The `HostApp` class uses the `FlashTrackBar` control on a Windows Form.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="efec1-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efec1-138">See also</span></span>

- <span data-ttu-id="efec1-139">[Erweitern der Entwurfszeitunterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="efec1-139">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- [<span data-ttu-id="efec1-140">Grundlagen für das Entwickeln von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="efec1-140">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)
