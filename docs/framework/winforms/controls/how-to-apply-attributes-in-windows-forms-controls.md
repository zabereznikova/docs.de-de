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
ms.openlocfilehash: 273d32927582f4467a92cd3b8f87e699c1f167d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922783"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente
Zum Entwickeln von Komponenten und Steuerelementen, die ordnungsgemäß mit der Entwurfs Umgebung interagieren und zur Laufzeit ordnungsgemäß ausgeführt werden, müssen Sie Attribute ordnungsgemäß auf Klassen und Member anwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie mehrere Attribute für ein benutzerdefiniertes Steuerelement verwendet werden. Das-Steuerelement veranschaulicht eine einfache Protokollierungsfunktion. Wenn das Steuerelement an eine Datenquelle gebunden ist, werden die Werte angezeigt, die von der Datenquelle <xref:System.Windows.Forms.DataGridView> in einem-Steuerelement gesendet werden. Wenn ein Wert den von der `Threshold` -Eigenschaft angegebenen Wert überschreitet, wird ein `ThresholdExceeded` -Ereignis ausgelöst.  
  
 Protokolliert Werte mit einer `LogEntry` -Klasse. `AttributesDemoControl` Die `LogEntry` -Klasse ist eine Vorlagen Klasse, d. h., Sie wird für den Typ parametrisiert, den Sie protokolliert. Wenn `AttributesDemoControl` z. b. Werte vom Typ `float`protokolliert, wird jede `LogEntry` Instanz wie folgt deklariert und verwendet.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> Da `LogEntry` durch einen beliebigen Typ parametrisiert wird, muss die Reflektion für den Parametertyp verwendet werden. Damit die Schwellenwert Funktion funktioniert, muss der Parametertyp `T` die <xref:System.IComparable> -Schnittstelle implementieren.  
  
 Das Formular, das als `AttributesDemoControl` Host für die Abfrage eines Leistungs Zählers in der Regel Jeder Wert wird in einem `LogEntry` des entsprechenden Typs verpackt und dem <xref:System.Windows.Forms.BindingSource>Formular hinzugefügt. Der `AttributesDemoControl` empfängt den Wert über seine Datenbindung und zeigt den Wert in einem <xref:System.Windows.Forms.DataGridView> -Steuerelement an.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Das erste Codebeispiel ist die `AttributesDemoControl` -Implementierung. Im zweiten Codebeispiel wird ein Formular veranschaulicht, das `AttributesDemoControl`verwendet.  
  
## <a name="class-level-attributes"></a>Attribute auf Klassenebene  
 Einige Attribute werden auf Klassenebene angewendet. Das folgende Codebeispiel zeigt die Attribute, die in der Regel auf ein Windows Forms Steuerelement angewendet werden.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter-Attribut  
 <xref:System.ComponentModel.TypeConverterAttribute>ist ein weiteres häufig verwendetes Attribut auf Klassenebene. Im folgenden Codebeispiel wird die Verwendung für die `LogEntry` -Klasse veranschaulicht. Dieses Beispiel zeigt auch eine Implementierung eines <xref:System.ComponentModel.TypeConverter> für den-Typ mit dem `LogEntryTypeConverter` `LogEntry` Namen.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Attribute auf Element Ebene  
 Einige Attribute werden auf der Element Ebene angewendet. Die folgenden Codebeispiele zeigen einige Attribute, die häufig auf Eigenschaften von Windows Forms-Steuerelementen angewendet werden.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue-Attribut  
 Das folgende Beispiel veranschaulicht das <xref:System.ComponentModel.AmbientValueAttribute> und zeigt Code, der seine Interaktion mit der Entwurfs Umgebung unterstützt. Diese Interaktion wird als *Ambiente*bezeichnet.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>DataBinding-Attribute  
 In den folgenden Beispielen wird eine Implementierung komplexer Daten Bindungen veranschaulicht. Die zuvor gezeigte Klassen <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>Ebene gibt die-Eigenschaft und `DataSource` die `DataMember` -Eigenschaft an, die für die Datenbindung verwendet werden sollen. Der <xref:System.ComponentModel.AttributeProviderAttribute> gibt den Typ an, an `DataSource` den die Eigenschaft gebunden wird.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Das Formular, das hostet `AttributesDemoControl` , erfordert einen Verweis auf die `AttributesDemoControl` Assembly, um zu erstellen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](developing-custom-windows-forms-controls.md)
- [Attribute in Windows Forms-Steuerelementen](attributes-in-windows-forms-controls.md)
- [Vorgehensweise: Serialisieren von Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
