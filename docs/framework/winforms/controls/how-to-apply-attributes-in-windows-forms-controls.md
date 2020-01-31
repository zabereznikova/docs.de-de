---
title: Anwenden von Attributen in Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: b8ecd516cf6bb189c6ad1b208dd8e3a5444f001c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741495"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="d35ce-102">Gewusst wie: Anwenden von Attributen auf Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="d35ce-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="d35ce-103">Zum Entwickeln von Komponenten und Steuerelementen, die ordnungsgemäß mit der Entwurfs Umgebung interagieren und zur Laufzeit ordnungsgemäß ausgeführt werden, müssen Sie Attribute ordnungsgemäß auf Klassen und Member anwenden.</span><span class="sxs-lookup"><span data-stu-id="d35ce-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d35ce-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d35ce-104">Example</span></span>  
 <span data-ttu-id="d35ce-105">Im folgenden Codebeispiel wird veranschaulicht, wie mehrere Attribute für ein benutzerdefiniertes Steuerelement verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d35ce-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="d35ce-106">Das-Steuerelement veranschaulicht eine einfache Protokollierungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="d35ce-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="d35ce-107">Wenn das Steuerelement an eine Datenquelle gebunden ist, zeigt es die Werte an, die von der Datenquelle in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d35ce-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d35ce-108">Wenn ein Wert den von der `Threshold`-Eigenschaft angegebenen Wert überschreitet, wird ein `ThresholdExceeded` Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d35ce-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="d35ce-109">Der `AttributesDemoControl` protokolliert Werte mit einer `LogEntry`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="d35ce-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="d35ce-110">Die `LogEntry`-Klasse ist eine Vorlagen Klasse, d. h., Sie wird für den Typ parametrisiert, den Sie protokolliert.</span><span class="sxs-lookup"><span data-stu-id="d35ce-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="d35ce-111">Wenn die `AttributesDemoControl` z. b. Werte vom Typ `float`protokolliert, wird jede `LogEntry` Instanz wie folgt deklariert und verwendet.</span><span class="sxs-lookup"><span data-stu-id="d35ce-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="d35ce-112">Da `LogEntry` durch einen beliebigen Typ parametrisiert wird, muss die Reflektion für den Parametertyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d35ce-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="d35ce-113">Damit die Funktion für den Schwellenwert funktioniert, muss der Parametertyp `T` die <xref:System.IComparable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="d35ce-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="d35ce-114">Das Formular, das den `AttributesDemoControl` hostet einen Leistungswert in regelmäßigen Abständen.</span><span class="sxs-lookup"><span data-stu-id="d35ce-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="d35ce-115">Jeder Wert wird in einem `LogEntry` des entsprechenden Typs verpackt und zum <xref:System.Windows.Forms.BindingSource>des Formulars hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d35ce-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="d35ce-116">Der `AttributesDemoControl` empfängt den Wert über seine Datenbindung und zeigt den Wert in einem <xref:System.Windows.Forms.DataGridView> Steuerelement an.</span><span class="sxs-lookup"><span data-stu-id="d35ce-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="d35ce-117">Das erste Codebeispiel ist die `AttributesDemoControl`-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="d35ce-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="d35ce-118">Im zweiten Codebeispiel wird ein Formular veranschaulicht, das die `AttributesDemoControl`verwendet.</span><span class="sxs-lookup"><span data-stu-id="d35ce-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="d35ce-119">Attribute auf Klassenebene</span><span class="sxs-lookup"><span data-stu-id="d35ce-119">Class-level Attributes</span></span>  
 <span data-ttu-id="d35ce-120">Einige Attribute werden auf Klassenebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="d35ce-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="d35ce-121">Das folgende Codebeispiel zeigt die Attribute, die in der Regel auf ein Windows Forms Steuerelement angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d35ce-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="d35ce-122">TypeConverter-Attribut</span><span class="sxs-lookup"><span data-stu-id="d35ce-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="d35ce-123"><xref:System.ComponentModel.TypeConverterAttribute> ist ein weiteres häufig verwendetes Attribut auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="d35ce-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="d35ce-124">Das folgende Codebeispiel zeigt die Verwendung für die `LogEntry`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="d35ce-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="d35ce-125">Dieses Beispiel zeigt auch eine Implementierung eines <xref:System.ComponentModel.TypeConverter> für den `LogEntry`-Typ, der `LogEntryTypeConverter`genannt wird.</span><span class="sxs-lookup"><span data-stu-id="d35ce-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="d35ce-126">Attribute auf Element Ebene</span><span class="sxs-lookup"><span data-stu-id="d35ce-126">Member-level Attributes</span></span>  
 <span data-ttu-id="d35ce-127">Einige Attribute werden auf der Element Ebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="d35ce-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="d35ce-128">Die folgenden Codebeispiele zeigen einige Attribute, die häufig auf Eigenschaften von Windows Forms-Steuerelementen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d35ce-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="d35ce-129">AmbientValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="d35ce-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="d35ce-130">Das folgende Beispiel veranschaulicht die <xref:System.ComponentModel.AmbientValueAttribute> und zeigt Code, der die Interaktion mit der Entwurfs Umgebung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d35ce-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="d35ce-131">Diese Interaktion wird als *Ambiente*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d35ce-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="d35ce-132">DataBinding-Attribute</span><span class="sxs-lookup"><span data-stu-id="d35ce-132">Databinding Attributes</span></span>  
 <span data-ttu-id="d35ce-133">In den folgenden Beispielen wird eine Implementierung komplexer Daten Bindungen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d35ce-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="d35ce-134">Der zuvor gezeigte <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>auf Klassenebene gibt die `DataSource` und `DataMember` Eigenschaften an, die für die Datenbindung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d35ce-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="d35ce-135">Der <xref:System.ComponentModel.AttributeProviderAttribute> der den Typ angibt, an den die `DataSource` Eigenschaft gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="d35ce-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d35ce-136">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d35ce-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="d35ce-137">Das Formular, das den `AttributesDemoControl` hostet, erfordert einen Verweis auf die `AttributesDemoControl` Assembly, um zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d35ce-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d35ce-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d35ce-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="d35ce-139">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d35ce-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="d35ce-140">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="d35ce-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="d35ce-141">[Gewusst wie: Serialisieren von Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d35ce-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
