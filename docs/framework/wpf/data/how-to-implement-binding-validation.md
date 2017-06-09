---
title: "Gewusst wie: Implementieren der Bindungsvalidierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Bindung, Überprüfung von"
  - "Datenbindung, Überprüfung der Bindung"
  - "Überprüfung der Bindung"
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: Implementieren der Bindungsvalidierung
Dieses Beispiel veranschaulicht die Verwendung eines <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und eines Formattriggers zum Bereitstellen von visuellem Feedback, um den Benutzer zu benachrichtigen, wenn basierend auf einer benutzerdefinierten Validierungsregel ein ungültiger Wert eingegeben wird.  
  
## Beispiel  
 Der Textinhalt von <xref:System.Windows.Controls.TextBox> im folgenden Beispiel ist an die `Age`\-Eigenschaft \(vom Typ int\) eines [Bindungsquellen](GTMT)\-Objekts mit dem Namen `ods` gebunden.  Die Bindung ist so eingerichtet, dass eine Validierungsregel mit dem Namen `AgeRangeRule` verwendet wird. Wenn der Benutzer ein nicht numerisches Zeichen oder einen Wert kleiner als 21 oder größer als 130 eingibt, werden neben dem Textfeld ein rotes Ausrufezeichen und eine QuickInfo mit einer Fehlermeldung angezeigt, wenn der Mauszeiger über das Textfeld geführt wird.  
  
 [!code-xml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 Das folgende Beispiel veranschaulicht die Implementierung von `AgeRangeRule`, die von <xref:System.Windows.Controls.ValidationRule> erbt und die <xref:System.Windows.Controls.ValidationRule.Validate%2A>\-Methode überschreibt.  Die Int32.Parse\(\)\-Methode wird für den Wert aufgerufen, um sicherzustellen, dass keine ungültigen Zeichen enthalten sind.  Die <xref:System.Windows.Controls.ValidationRule.Validate%2A>\-Methode gibt ein <xref:System.Windows.Controls.ValidationResult> zurück, das angibt, ob der Wert gültig ist. Dies basiert darauf, ob während der Analyse eine Ausnahme ausgelöst wird und ob der Alterswert außerhalb der Unter\- und Obergrenzen liegt.  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 Das folgende Beispiel zeigt das benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`, mit dem ein rotes Ausrufezeichen erstellt wird, das den Benutzer auf einen Fehler bei der Validierung hinweist.  Steuerelementvorlagen werden verwendet, um die Darstellung eines Steuerelements neu zu definieren.  
  
 [!code-xml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 Wie im folgenden Beispiel dargestellt, wird der <xref:System.Windows.Controls.ToolTip> mit der Fehlermeldung mit dem `textBoxInError`\-Stil erstellt.  Wenn der Wert von <xref:System.Windows.Controls.Validation.HasError%2A> `true` ist, legt der Trigger die QuickInfo des aktuellen <xref:System.Windows.Controls.TextBox> auf den ersten Validierungsfehler fest.  Die <xref:System.Windows.Data.Binding.RelativeSource%2A> wird auf <xref:System.Windows.Data.RelativeSourceMode> festgelegt und verweist so auf das aktuelle Element.  
  
 [!code-xml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
 Beachten Sie Folgendes: Wenn Sie kein benutzerdefiniertes <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> bereitstellen, wird dem Benutzer durch die standardmäßige Fehlervorlage visuelles Feedback gegeben, wenn ein Validierungsfehler vorliegt.  Weitere Informationen finden Sie unter "Datenvalidierung" in [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet außerdem eine integrierte Validierungsregel, die die während der Aktualisierung der Bindungsquelleneigenschaft ausgelöste Ausnahmen abfängt.  Weitere Informationen finden Sie unter <xref:System.Windows.Controls.ExceptionValidationRule>.  
  
## Siehe auch  
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)