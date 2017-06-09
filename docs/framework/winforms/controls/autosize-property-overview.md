---
title: "&#220;bersicht &#252;ber die AutoSize-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Automatische Größenanpassung"
  - "AutoSize-Eigenschaft"
  - "AutoSizeMode-Eigenschaft"
  - "Layout [Windows Forms], AutoSize"
  - "Größe anpassen, Automatisch"
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# &#220;bersicht &#252;ber die AutoSize-Eigenschaft
Die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft ermöglicht es einem Steuerelement, bei Bedarf seine Größe an den durch die <xref:System.Windows.Forms.Control.PreferredSize%2A>\-Eigenschaft festgelegten Wert anzupassen.  Sie stellen das Größenanpassungsverhalten für bestimmte Steuerelemente ein, indem Sie die `AutoSizeMode`\-Eigenschaft festlegen.  
  
## Das AutoSize\-Verhalten  
 Nur einige Steuerelemente unterstützen die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft.  Außerdem unterstützen einige Steuerelemente, die die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft unterstützen, auch die `AutoSizeMode`\-Eigenschaft.  
  
 Die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft löst je nach Steuerelementtyp und Wert der `AutoSizeMode`\-Eigenschaft, falls vorhanden, ein geringfügig anderes Verhalten aus.  Die folgende Tabelle enthält die Verhalten, die immer zutreffen, sowie eine kurze Beschreibung der jeweiligen Verhalten.  
  
|Immer zutreffendes Verhalten|Beschreibung|  
|----------------------------------|------------------|  
|Die automatische Größenanpassung ist ein Laufzeitfeature.|Dies bedeutet, dass ein Steuerelement dadurch nie vergrößert oder verkleinert wird und somit keine weiteren Auswirkungen hat.|  
|Wenn sich die Größe eines Steuerelements ändert, bleibt der Wert seiner <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft immer konstant.|Wenn ein Steuerelement aufgrund seines Inhalts vergrößert wird, erfolgt die Größenanpassung nach rechts und nach unten.  Steuerelemente werden nicht nach links vergrößert.|  
|Die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft und die <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft werden berücksichtigt, wenn <xref:System.Windows.Forms.Control.AutoSize%2A> auf `true` festgelegt ist.|Der Wert der <xref:System.Windows.Forms.Control.Location%2A>\-Eigenschaft des Steuerelements wird an den richtigen Wert angepasst.<br /><br /> **Hinweis** Das <xref:System.Windows.Forms.Label>\-Steuerelement stellt die Ausnahme von dieser Regel dar.  Wenn Sie den Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft eines angedockten <xref:System.Windows.Forms.Label>\-Steuerelements auf `true` festlegen, wird das <xref:System.Windows.Forms.Label>\-Steuerelement nicht gestreckt.|  
|Die <xref:System.Windows.Forms.Control.MaximumSize%2A>\-Eigenschaft und die <xref:System.Windows.Forms.Control.MinimumSize%2A>\-Eigenschaft eines Steuerelements werden stets berücksichtigt, unabhängig vom Wert der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft.|Die <xref:System.Windows.Forms.Control.MaximumSize%2A>\-Eigenschaft und die <xref:System.Windows.Forms.Control.MinimumSize%2A>\-Eigenschaft werden von der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft nicht beeinflusst.|  
|Standardmäßig ist keine Mindestgröße festgelegt.|Wenn ein Steuerelement bei Verwendung von <xref:System.Windows.Forms.Control.AutoSize%2A> verkleinert wird, jedoch über keinen Inhalt verfügt, lautet der Wert der <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft 0,0.  In diesem Fall wird das Steuerelement bis zu einem gewissen Punkt verkleinert und ist nicht ohne weiteres sichtbar.|  
|Wenn ein Steuerelement die <xref:System.Windows.Forms.Control.GetPreferredSize%2A>\-Methode nicht implementiert, gibt die <xref:System.Windows.Forms.Control.GetPreferredSize%2A>\-Methode den letzten Wert zurück, der der <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft zugewiesen wurde.|Wenn Sie also <xref:System.Windows.Forms.Control.AutoSize%2A> auf `true` festlegen, hat dies keine Auswirkungen.|  
|Ein Steuerelement in einer <xref:System.Windows.Forms.TableLayoutPanel>\-Zelle passt sich stets der Größe der Zelle an, bis seine <xref:System.Windows.Forms.Control.MinimumSize%2A> erreicht ist.|Diese Größe wird als maximale Größe erzwungen.  Dies ist nicht der Fall, wenn die Zelle Teil einer <xref:System.Windows.Forms.SizeType>\-Zeile oder \-Spalte ist.|  
  
## AutoSizeMode\-Eigenschaft  
 Die `AutoSizeMode`\-Eigenschaft ermöglicht eine genauere Kontrolle über das standardmäßige <xref:System.Windows.Forms.Control.AutoSize%2A>\-Verhalten.  Die `AutoSizeMode`\-Eigenschaft gibt an, wie sich die Größe eines Steuerelements an dessen Inhalt anpasst.  Bei dem Inhalt könnte es sich beispielsweise um den Text für ein <xref:System.Windows.Forms.Button>\-Steuerelement oder die untergeordneten Steuerelemente für einen Container handeln.  
  
 Die folgende Tabelle zeigt die <xref:System.Windows.Forms.AutoSizeMode>\-Einstellungen und eine Beschreibung des Verhaltens, das jede Einstellung auslöst.  
  
|AutoSizeMode\-Einstellung|Verhalten|  
|-------------------------------|---------------|  
|GrowAndShrink|Das Steuerelement wird vergrößert oder verkleinert, sodass es seinen Inhalt umgibt.<br /><br /> Der <xref:System.Windows.Forms.Control.MinimumSize%2A>\-Wert und der <xref:System.Windows.Forms.Control.MaximumSize%2A>\-Wert werden berücksichtigt, der aktuelle Wert der <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft wird jedoch ignoriert.<br /><br /> Dies ist das gleiche Verhalten wie das von Steuerelementen mit der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft und keiner `AutoSizeMode`\-Eigenschaft.|  
|GrowOnly|Das Steuerelement wird vergrößert, bis es seinen Inhalt umgibt, jedoch maximal bis zum Wert der <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft verkleinert.<br /><br /> Dies ist der Standardwert für `AutoSizeMode`.|  
  
## Steuerelemente, die die AutoSize\-Eigenschaft unterstützen  
 In der folgenden Tabelle werden die Steuerelemente aufgelistet, die die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft und die `AutoSizeMode`\-Eigenschaft unterstützen.  
  
|AutoSize\-Unterstützung|Steuerelementtyp|  
|-----------------------------|----------------------|  
|-   Die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft wird unterstützt.<br />-   Keine `AutoSizeMode`\-Eigenschaft.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox> \(<xref:System.Windows.Forms.TextBox>\-Basis\)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   Die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft wird unterstützt.<br />-   Die `AutoSizeMode`\-Eigenschaft wird unterstützt.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-   Keine <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## AutoSize in der Entwurfsumgebung  
 In der folgenden Tabelle wird das Größenanpassungsverhalten eines Steuerelements zur Entwurfszeit beschrieben, das auf dem Wert seiner <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft und seiner `AutoSizeMode`\-Eigenschaft basiert.  
  
 Überschreiben Sie die <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A>\-Eigenschaft, um herauszufinden, ob ein bestimmtes Steuerelement vom Benutzer angepasst werden kann.  In der folgenden Tabelle bedeutet "kann nicht" lediglich <xref:System.Windows.Forms.Design.SelectionRules>, während "kann" <xref:System.Windows.Forms.Design.SelectionRules> und <xref:System.Windows.Forms.Design.SelectionRules> bedeutet.  
  
|AutoSize\-Einstellungen|Größenanpassung zur Entwurfszeit|  
|-----------------------------|--------------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   Keine `AutoSizeMode`\-Eigenschaft.|Der Benutzer kann die Größe des Steuerelements zur Entwurfszeit nicht ändern, außer bei folgenden Steuerelementen:<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   `AutoSizeMode` \= <xref:System.Windows.Forms.AutoSizeMode>|Der Benutzer kann die Größe des Steuerelements zur Entwurfszeit nicht ändern.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   `AutoSizeMode` \= <xref:System.Windows.Forms.AutoSizeMode>|Der Benutzer kann die Größe des Steuerelements zur Entwurfszeit ändern.  Wenn die <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft festgelegt ist, kann der Benutzer die Größe des Steuerelements lediglich erhöhen.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `false`, oder die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft ist verborgen.|Der Benutzer kann die Größe des Steuerelements zur Entwurfszeit ändern.|  
  
> [!NOTE]
>  Um die Produktivität zu maximieren, führt der Windows Forms\-Designer für die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft der <xref:System.Windows.Forms.Form>\-Klasse Shadowing durch.  Zur Entwurfszeit verhält sich das Formular, als ob die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft auf `false` festgelegt sei, und zwar unabhängig von seiner eigentlichen Einstellung.  Zur Laufzeit werden keine speziellen Anpassungen vorgenommen, und die <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft wird entsprechend der Eigenschafteneinstellung angewendet.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.Control.PreferredSize%2A>   
 <xref:System.Windows.Forms.Control.GetPreferredSize%2A>