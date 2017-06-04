---
title: "Gewusst wie: Erstellen eines Windows Forms-Steuerelements, das den Fortschritt anzeigt | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Erstellen"
  - "Steuerelemente [Windows Forms], Statusverfolgung"
  - "FlashTrackBar (benutzerdefiniertes Steuerelement)"
  - "Status, Berichterstellung [Windows Forms]"
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen eines Windows Forms-Steuerelements, das den Fortschritt anzeigt
Im folgenden Codebeispiel wird ein benutzerdefiniertes Steuerelement mit dem Namen `FlashTrackBar` gezeigt, das verwendet werden kann, um den Fortschritt einer Anwendung anzuzeigen.  Der Fortschritt wird mithilfe eines Farbverlaufs visuell dargestellt.  
  
 Das `FlashTrackBar`\-Steuerelement veranschaulicht folgende Konzepte:  
  
-   Das Definieren benutzerdefinierter Eigenschaften.  
  
-   Das Definieren benutzerdefinierter Ereignisse.  \(`FlashTrackBar` definiert das `ValueChanged`\-Ereignis.\)  
  
-   Das Überschreiben der <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode, um Logik zum Zeichnen des Steuerelements bereitzustellen.  
  
-   Das Berechnen des Bereichs, der zum Zeichnen des Steuerelements zur Verfügung steht, indem die <xref:System.Windows.Forms.Control.ClientRectangle%2A>\-Eigenschaft verwendet wird.  `FlashTrackBar` führt dies in der dazugehörigen `OptimizedInvalidate`\-Methode aus.  
  
-   Implementieren der Serialisierung oder Dauerhaftigkeit für eine Eigenschaft, wenn sie im Windows Forms\-Designer geändert wird.  `FlashTrackBar` definiert die `ShouldSerializeStartColor`\-Methode und die `ShouldSerializeEndColor`\-Methode für die Serialisierung der dazugehörigen `StartColor`\-Eigenschaft und `EndColor`\-Eigenschaft.  
  
 Die folgende Tabelle enthält die benutzerdefinierten Eigenschaften, die durch `FlashTrackBar` definiert sind.  
  
|Property|Beschreibung|  
|--------------|------------------|  
|`AllowUserEdit`|Zeigt an, ob der Benutzer den Wert der Flashtrackleiste ändern kann, indem er darauf klickt und zieht.|  
|`EndColor`|Gibt die Farbe am Ende der Trackleiste an.|  
|`DarkenBy`|Gibt an, wie stark der Hintergrund im Vergleich zum Farbverlauf des Vordergrunds abgedunkelt werden muss.|  
|`Max`|Gibt den höchsten Wert der Trackleiste an.|  
|`Min`|Gibt den niedrigsten Wert der Trackleiste an.|  
|`StartColor`|Gibt die Anfangsfarbe des Farbverlaufs an.|  
|`ShowPercentage`|Gibt an, ob über dem Farbverlauf eine Prozentangabe angezeigt wird.|  
|`ShowValue`|Gibt an, ob über dem Farbverlauf der aktuelle Wert angezeigt wird.|  
|`ShowGradient`|Gibt an, ob in der Trackleiste ein Farbverlauf für den aktuellen Wert angezeigt wird.|  
|-   `Value`|Gibt den aktuellen Wert der Trackleiste an.|  
  
 Die folgende Tabelle enthält zusätzliche Member, die definiert sind durch das `FlashTrackBar:`\-Ereignis, das durch eine Eigenschaftenänderung ausgelöst wird, und die Methode, die das Ereignis auslöst.  
  
|Member|Beschreibung|  
|------------|------------------|  
|`ValueChanged`|Das Ereignis, das ausgelöst wird, wenn sich die `Value`\-Eigenschaft der Trackleiste ändert.|  
|`OnValueChanged`|Die Methode, die das `ValueChanged`\-Ereignis auslöst.|  
  
> [!NOTE]
>  `FlashTrackBar` verwendet die <xref:System.EventArgs>\-Klasse für Ereignisdaten und <xref:System.EventHandler> für den Ereignisdelegaten.  
  
 Zur Behandlung der entsprechenden *EventName*\-Ereignisse überschreibt `FlashTrackBar` die folgenden von <xref:System.Windows.Forms.Control?displayProperty=fullName> geerbten Methoden:  
  
-   <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
-   <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
-   <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 `FlashTrackBar` überschreibt die folgenden von <xref:System.Windows.Forms.Control?displayProperty=fullName> geerbten Methoden, um die entsprechenden, anhand von Eigenschaften geänderten Ereignisse zu behandeln:  
  
-   <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
-   <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## Beispiel  
 Das `FlashTrackBar`\-Steuerelement definiert zwei UI\-Typ\-Editoren, `FlashTrackBarValueEditor` und `FlashTrackBarDarkenByEditor`, die in der folgenden Codeliste enthalten sind.  Die `HostApp`\-Klasse verwendet das `FlashTrackBar`\-Steuerelement in einem Windows Form.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## Siehe auch  
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Grundlagen für das Entwickeln von Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)