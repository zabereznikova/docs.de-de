---
title: "Gewusst wie: Anwenden von Attributen auf Windows Forms-Steuerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Attribute [Windows Forms], Übernehmen"
  - "Steuerelemente [Windows Forms], Übernehmen von Attributen"
  - "Windows Forms-Steuerelemente, Übernehmen von Attributen"
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Gewusst wie: Anwenden von Attributen auf Windows Forms-Steuerelemente
Um Komponenten und Steuerelemente zu entwickeln, die einwandfrei mit der Entwurfsumgebung interagieren und zur Laufzeit ordnungsgemäß ausgeführt werden, müssen Sie die entsprechenden Attribute auf Klassen und Member anwenden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie verschiedene Attribute für ein benutzerdefiniertes Steuerelement verwendet werden.  Das Steuerelement weist eine einfache Protokollfunktion auf.  Wenn das Steuerelement an eine Datenquelle gebunden ist, zeigt es die Werte an, die von der Datenquelle in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement gesendet wurden.  Wenn ein Wert den durch die `Threshold`\-Eigenschaft festgelegten Wert übersteigt, wird ein `ThresholdExceeded`\-Ereignis ausgelöst.  
  
 Das `AttributesDemoControl` protokolliert Werte mit einer `LogEntry`\-Klasse.  Die `LogEntry`\-Klasse ist eine Vorlagenklasse, d. h. sie wird für den Typ, den sie protokolliert, parametrisiert.  Wenn das `AttributesDemoControl` beispielsweise Werte des Typs `float` protokolliert, wird jede `LogEntry`\-Instanz deklariert und wie folgt verwendet.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  Da `LogEntry` von einem beliebigen Typ parametrisiert wird, muss sie Reflektion verwenden, damit sie für den Parametertyp verwendet werden kann.  Damit das Schwellenwertfeature funktioniert, muss der Parametertyp, `T` die <xref:System.IComparable>\-Schnittstelle implementieren.  
  
 Das Formular, das das `AttributesDemoControl` hostet, fragt in regelmäßigen Abständen einen Leistungsindikator ab.  Jeder Wert wird in einen `LogEntry` des entsprechenden Typs gepackt und der <xref:System.Windows.Forms.BindingSource> des Formulars hinzugefügt.  Das `AttributesDemoControl` empfängt den Wert mithilfe seiner Datenbindung und zeigt den Wert in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement an.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Das erste Codebeispiel ist die `AttributesDemoControl`\-Implementierung.  Das zweite Codebeispiel veranschaulicht ein Formular, das das `AttributesDemoControl` verwendet.  
  
## Attribute auf Klassenebene  
 Einige Attribute werden auf Klassenebene zugewiesen.  Im folgenden Codebeispiel werden die Attribute gezeigt, die im Allgemeinen auf ein Windows Forms\-Steuerelement angewendet werden.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### TypeConverter\-Attribut  
 <xref:System.ComponentModel.TypeConverterAttribute> ist ein weiteres häufig verwendetes Attribut auf Klassenebene.  Im folgenden Codebeispiel wird seine Verwendung für die `LogEntry`\-Klasse veranschaulicht.  In diesem Beispiel wird außerdem die Implementierung eines <xref:System.ComponentModel.TypeConverter> für den `LogEntry`\-Typ gezeigt, der so genannte `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## Attribute auf Memberebene  
 Einige Attribute werden auf Memberebene zugewiesen.  Die folgenden Codebeispiele zeigen einige Attribute, die im Allgemeinen auf Eigenschaften von Windows Forms\-Steuerelementen angewendet werden  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### AmbientValue\-Attribut  
 Das folgende Beispiel veranschaulicht das <xref:System.ComponentModel.AmbientValueAttribute> und zeigt Code, der seine Interaktion mit der Entwurfsumgebung unterstützt.  Diese Interaktion wird als *Umgebung* bezeichnet.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### Datenbindungsattribute  
 Die folgenden Beispiele zeigen die Implementierung einer komplexen Datenbindung.  Das zuvor gezeigte <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> auf Klassenebene legt die `DataSource`\-Eigenschaft und `DataMember`\-Eigenschaft fest, die zur Datenbindung verwendet werden sollen.  Das <xref:System.ComponentModel.AttributeProviderAttribute> legt den Typ fest, an den die `DataSource`\-Eigenschaft gebunden wird.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## Kompilieren des Codes  
  
-   Das Formular, das das `AttributesDemoControl` hostet, benötigt zur Erstellung einen Verweis auf die `AttributesDemoControl`\-Assembly.  
  
## Siehe auch  
 <xref:System.IComparable>   
 <xref:System.Windows.Forms.DataGridView>   
 [Entwickeln benutzerdefinierter Windows Forms\-Steuerelemente mit .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Attribute in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)   
 [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md)