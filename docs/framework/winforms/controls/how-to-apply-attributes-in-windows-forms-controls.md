---
title: 'Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: e86277c06e515b28bada3331cf4fd63e536319a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079590"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="b67c5-102">Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="b67c5-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="b67c5-103">Zum Entwickeln von Komponenten und Steuerelementen, die die entwurfsumgebung ordnungsgemäß interagieren und zur Laufzeit ordnungsgemäß ausgeführt werden, müssen Sie Attribute ordnungsgemäß auf Klassen und Member anwenden.</span><span class="sxs-lookup"><span data-stu-id="b67c5-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b67c5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b67c5-104">Example</span></span>  
 <span data-ttu-id="b67c5-105">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mehrere Attribute in ein benutzerdefiniertes Steuerelement zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b67c5-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="b67c5-106">Das Steuerelement zeigt eine einfache Protokollierungsfunktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b67c5-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="b67c5-107">Wenn das Steuerelement an eine Datenquelle gebunden ist, zeigt es die Werte, die gesendet werden, von der Datenquelle in einem <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b67c5-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b67c5-108">Wenn ein Wert den angegebenen Wert übersteigt den `Threshold` -Eigenschaft, ein `ThresholdExceeded` Ereignis wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b67c5-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="b67c5-109">Die `AttributesDemoControl` protokolliert Werte mit einer `LogEntry` Klasse.</span><span class="sxs-lookup"><span data-stu-id="b67c5-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="b67c5-110">Die `LogEntry` -Klasse ist eine Vorlagenklasse, was bedeutet es für den Typ, den sie protokolliert parametrisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b67c5-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="b67c5-111">Z. B. wenn die `AttributesDemoControl` ist die Protokollierung von Werten des Typs `float`, die jeweils `LogEntry` Instanz deklariert und wie folgt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b67c5-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="b67c5-112">Da `LogEntry` parametrisiert wird durch einen beliebigen Typ, es muss mithilfe von Reflektion für den Parametertyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b67c5-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="b67c5-113">Für die Schwellenwert-Funktion funktioniert, den Parametertyp `T` müssen implementieren die <xref:System.IComparable> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b67c5-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="b67c5-114">Das Formular, hostet die `AttributesDemoControl` einen Leistungsindikator in regelmäßigen Abständen abgefragt.</span><span class="sxs-lookup"><span data-stu-id="b67c5-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="b67c5-115">Jeder Wert ist innerhalb einer `LogEntry` des entsprechenden Typs und des Formulars hinzugefügt <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="b67c5-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="b67c5-116">Die `AttributesDemoControl` empfängt den Wert durch die Datenbindung und zeigt den Wert in eine <xref:System.Windows.Forms.DataGridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b67c5-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="b67c5-117">Im erste Codebeispiel wird die `AttributesDemoControl` Implementierung.</span><span class="sxs-lookup"><span data-stu-id="b67c5-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="b67c5-118">Im zweiten Codebeispiel wird veranschaulicht, ein Formulars, verwendet der `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="b67c5-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="b67c5-119">Klassenattribute</span><span class="sxs-lookup"><span data-stu-id="b67c5-119">Class-level Attributes</span></span>  
 <span data-ttu-id="b67c5-120">Es werden einige Attribute auf Klassenebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="b67c5-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="b67c5-121">Das folgende Codebeispiel zeigt die Attribute, die häufig auf einem Windows Forms-Steuerelement angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b67c5-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="b67c5-122">TypeConverter-Attribut</span><span class="sxs-lookup"><span data-stu-id="b67c5-122">TypeConverter Attribute</span></span>  
 <xref:System.ComponentModel.TypeConverterAttribute> <span data-ttu-id="b67c5-123">ist eine andere häufig verwendetes auf Klassenebene-Attribut.</span><span class="sxs-lookup"><span data-stu-id="b67c5-123">is another commonly used class-level attribute.</span></span> <span data-ttu-id="b67c5-124">Im folgenden Codebeispiel wird veranschaulicht, dessen Verwendung in der `LogEntry` Klasse.</span><span class="sxs-lookup"><span data-stu-id="b67c5-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="b67c5-125">Dieses Beispiel zeigt auch eine Implementierung von einem <xref:System.ComponentModel.TypeConverter> für die `LogEntry` Typs mit der Bezeichnung `LogEntryTypeConverter`.</span><span class="sxs-lookup"><span data-stu-id="b67c5-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="b67c5-126">Attribute auf Memberebene</span><span class="sxs-lookup"><span data-stu-id="b67c5-126">Member-level Attributes</span></span>  
 <span data-ttu-id="b67c5-127">Einige Attribute werden auf der Ebene des Elements angewendet.</span><span class="sxs-lookup"><span data-stu-id="b67c5-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="b67c5-128">Der folgende Code veranschaulicht einige Attribute, die im allgemeinen Eigenschaften des Windows Forms-Steuerelemente angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b67c5-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="b67c5-129">AmbientValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="b67c5-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="b67c5-130">Das folgende Beispiel zeigt die <xref:System.ComponentModel.AmbientValueAttribute> und zeigt Code, der die Interaktion mit der entwurfsumgebung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b67c5-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="b67c5-131">Diese Interaktion heißt *Umgebung*.</span><span class="sxs-lookup"><span data-stu-id="b67c5-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="b67c5-132">DataBinding-Attribute</span><span class="sxs-lookup"><span data-stu-id="b67c5-132">Databinding Attributes</span></span>  
 <span data-ttu-id="b67c5-133">Die folgenden Beispiele veranschaulichen eine Implementierung der komplexe Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="b67c5-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="b67c5-134">Klassenebene <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, wie gezeigt zuvor, gibt die `DataSource` und `DataMember` Eigenschaften, die für die Datenbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b67c5-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="b67c5-135">Die <xref:System.ComponentModel.AttributeProviderAttribute> gibt den Typ, der die `DataSource` Eigenschaft zu binden.</span><span class="sxs-lookup"><span data-stu-id="b67c5-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b67c5-136">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b67c5-136">Compiling the Code</span></span>  
  
-   <span data-ttu-id="b67c5-137">Das Formular, hostet die `AttributesDemoControl` erfordert einen Verweis auf die `AttributesDemoControl` Assembly, um zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b67c5-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b67c5-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b67c5-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="b67c5-139">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b67c5-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="b67c5-140">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="b67c5-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="b67c5-141">Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="b67c5-141">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
