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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079590"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente
Zum Entwickeln von Komponenten und Steuerelementen, die die entwurfsumgebung ordnungsgemäß interagieren und zur Laufzeit ordnungsgemäß ausgeführt werden, müssen Sie Attribute ordnungsgemäß auf Klassen und Member anwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie mehrere Attribute in ein benutzerdefiniertes Steuerelement zu verwenden. Das Steuerelement zeigt eine einfache Protokollierungsfunktionen zur Verfügung. Wenn das Steuerelement an eine Datenquelle gebunden ist, zeigt es die Werte, die gesendet werden, von der Datenquelle in einem <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn ein Wert den angegebenen Wert übersteigt den `Threshold` -Eigenschaft, ein `ThresholdExceeded` Ereignis wird ausgelöst.  
  
 Die `AttributesDemoControl` protokolliert Werte mit einer `LogEntry` Klasse. Die `LogEntry` -Klasse ist eine Vorlagenklasse, was bedeutet es für den Typ, den sie protokolliert parametrisiert wird. Z. B. wenn die `AttributesDemoControl` ist die Protokollierung von Werten des Typs `float`, die jeweils `LogEntry` Instanz deklariert und wie folgt verwendet wird.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  Da `LogEntry` parametrisiert wird durch einen beliebigen Typ, es muss mithilfe von Reflektion für den Parametertyp verwendet werden. Für die Schwellenwert-Funktion funktioniert, den Parametertyp `T` müssen implementieren die <xref:System.IComparable> Schnittstelle.  
  
 Das Formular, hostet die `AttributesDemoControl` einen Leistungsindikator in regelmäßigen Abständen abgefragt. Jeder Wert ist innerhalb einer `LogEntry` des entsprechenden Typs und des Formulars hinzugefügt <xref:System.Windows.Forms.BindingSource>. Die `AttributesDemoControl` empfängt den Wert durch die Datenbindung und zeigt den Wert in eine <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Im erste Codebeispiel wird die `AttributesDemoControl` Implementierung. Im zweiten Codebeispiel wird veranschaulicht, ein Formulars, verwendet der `AttributesDemoControl`.  
  
## <a name="class-level-attributes"></a>Klassenattribute  
 Es werden einige Attribute auf Klassenebene angewendet. Das folgende Codebeispiel zeigt die Attribute, die häufig auf einem Windows Forms-Steuerelement angewendet werden.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter-Attribut  
 <xref:System.ComponentModel.TypeConverterAttribute> ist eine andere häufig verwendetes auf Klassenebene-Attribut. Im folgenden Codebeispiel wird veranschaulicht, dessen Verwendung in der `LogEntry` Klasse. Dieses Beispiel zeigt auch eine Implementierung von einem <xref:System.ComponentModel.TypeConverter> für die `LogEntry` Typs mit der Bezeichnung `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Attribute auf Memberebene  
 Einige Attribute werden auf der Ebene des Elements angewendet. Der folgende Code veranschaulicht einige Attribute, die im allgemeinen Eigenschaften des Windows Forms-Steuerelemente angewendet werden.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue-Attribut  
 Das folgende Beispiel zeigt die <xref:System.ComponentModel.AmbientValueAttribute> und zeigt Code, der die Interaktion mit der entwurfsumgebung unterstützt. Diese Interaktion heißt *Umgebung*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>DataBinding-Attribute  
 Die folgenden Beispiele veranschaulichen eine Implementierung der komplexe Datenbindung. Klassenebene <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, wie gezeigt zuvor, gibt die `DataSource` und `DataMember` Eigenschaften, die für die Datenbindung verwendet. Die <xref:System.ComponentModel.AttributeProviderAttribute> gibt den Typ, der die `DataSource` Eigenschaft zu binden.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Das Formular, hostet die `AttributesDemoControl` erfordert einen Verweis auf die `AttributesDemoControl` Assembly, um zu erstellen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
- [Attribute in Windows Forms-Steuerelementen](attributes-in-windows-forms-controls.md)
- [Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
