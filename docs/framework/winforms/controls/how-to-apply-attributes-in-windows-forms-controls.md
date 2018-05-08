---
title: 'Gewusst wie: Anwenden von Attributen auf Windows Forms-Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 49c2aaa48a48e33a71b5112db31991975011551d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Gewusst wie: Anwenden von Attributen auf Windows Forms-Steuerelemente
Zum Entwickeln von Komponenten und Steuerelementen, die die entwurfsumgebung ordnungsgemäß interagieren und zur Laufzeit ordnungsgemäß ausgeführt, müssen Sie Attribute ordnungsgemäß auf Klassen und Member anwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie mehrere Attribute für ein benutzerdefiniertes Steuerelement zu verwenden. Das Steuerelement zeigt eine einfache Protokollierungsfunktionen. Wenn das Steuerelement an eine Datenquelle gebunden ist, zeigt es die Werte, die gesendet, von der Datenquelle in einem <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn ein Wert den angegebenen Wert übersteigt das `Threshold` -Eigenschaft, ein `ThresholdExceeded` Ereignis wird ausgelöst.  
  
 Die `AttributesDemoControl` protokolliert Werte mit einer `LogEntry` Klasse. Die `LogEntry` -Klasse ist eine Vorlagenklasse, d. h., er ist für den Typ, der protokolliert parametrisiert. Z. B. wenn die `AttributesDemoControl` ist die Protokollierung von Werten des Typs `float`, die jeweils `LogEntry` Instanz deklariert und wie folgt verwendet wird.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  Da `LogEntry` parametrisiert wird von einem beliebigen Typ muss es mithilfe der Reflektion für den Parametertyp ausgeführt werden. Für das Schwellenwertfeature funktioniert, den Parametertyp `T` implementieren müssen die <xref:System.IComparable> Schnittstelle.  
  
 Das Formular, hostet die `AttributesDemoControl` einen Leistungsindikator in regelmäßigen Abständen abgefragt. Jeder Wert wird verpackt in einer `LogEntry` des entsprechenden Typs und des Formulars hinzugefügt <xref:System.Windows.Forms.BindingSource>. Die `AttributesDemoControl` erhält den Wert durch die Datenbindung und zeigt den Wert in einem <xref:System.Windows.Forms.DataGridView> Steuerelement.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Im erste Codebeispiel wird die `AttributesDemoControl` Implementierung. Im zweiten Codebeispiel wird veranschaulicht, ein Formulars, verwendet die `AttributesDemoControl`.  
  
## <a name="class-level-attributes"></a>Attribute auf Klassenebene  
 Es werden einige Attribute auf Klassenebene angewendet. Das folgende Codebeispiel zeigt die Attribute, die häufig auf ein Windows Forms-Steuerelement angewendet werden.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>TypeConverter-Attribut  
 <xref:System.ComponentModel.TypeConverterAttribute> ist eine andere häufig verwendetes auf Klassenebene-Attribut. Im folgenden Codebeispiel wird gezeigt, Verwendungsmöglichkeiten für die `LogEntry` Klasse. Dieses Beispiel zeigt außerdem eine Implementierung von einem <xref:System.ComponentModel.TypeConverter> für die `LogEntry` Typ, mit dem Namen `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Attribute auf Memberebene  
 Einige Attribute werden auf Memberebene angewendet. Die folgenden Codebeispiele zeigen einige Attribute, die häufig auf Eigenschaften eines Windows Forms-Steuerelemente angewendet werden.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>AmbientValue-Attribut  
 Das folgende Beispiel veranschaulicht die <xref:System.ComponentModel.AmbientValueAttribute> und enthält Code, der seine Interaktion mit der entwurfsumgebung unterstützt. Diese Interaktion heißt *Umgebung*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>DataBinding-Attribute  
 Die folgenden Beispiele veranschaulichen eine Implementierung der komplexe Datenbindung. Der Klassenebene <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>wie zuvor, gibt die `DataSource` und `DataMember` Eigenschaften, die für die Datenbindung verwendet. Die <xref:System.ComponentModel.AttributeProviderAttribute> gibt den Typ, der die `DataSource` Eigenschaft zu binden.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Das Formular, hostet die `AttributesDemoControl` erfordert einen Verweis auf die `AttributesDemoControl` Assembly um erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Attribute in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
