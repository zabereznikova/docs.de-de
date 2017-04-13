---
title: "Gewusst wie: Implementieren von PriorityBinding | Microsoft Docs"
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
  - "Klassen, PriorityBinding"
  - "Datenbindung, PriorityBinding-Klasse"
  - "PriorityBinding-Klasse"
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Implementieren von PriorityBinding
<xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funktioniert durch Angabe einer Liste von Bindungen.  Die folgende Liste der Bindungen ist absteigend nach Priorität geordnet.  Wenn die Bindung mit der höchsten Priorität erfolgreich einen Wert zurückgibt, wenn sie verarbeitet wird, dann müssen die anderen Bindungen in der Liste nicht mehr verarbeitet werden.  Möglicherweise nimmt die Auswertung der Bindung mit der höchsten Priorität einige Zeit in Anspruch. Es wird so lange die Bindung mit der nächsten Priorität, die erfolgreich einen Wert zurückgibt, verwendet, bis eine Bindung mit einer höheren Priorität einen Wert erfolgreich zurückgibt.  
  
## Beispiel  
 Um die Funktionsweise von <xref:System.Windows.Data.PriorityBinding> zu veranschaulichen, wurde das `AsyncDataSource`\-Objekt mit den folgenden drei Eigenschaften erstellt: `FastDP`, `SlowerDP` und `SlowestDP`.  
  
 Der get\-Accessor von `FastDP` gibt den Wert des `_fastDP`\-Datenmembers zurück.  
  
 Der get\-Accessor von `SlowerDP` wartet 3 Sekunden, bevor der Wert des `_slowerDP`\-Datenmembers zurückgegeben wird.  
  
 Der get\-Accessor von `SlowestDP` wartet 5 Sekunden, bevor der Wert des `_slowestDP`\-Datenmembers zurückgegeben wird.  
  
> [!NOTE]
>  Dieses Beispiel dient nur der Veranschaulichung.  In den [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]\-Richtlinien wird die Definition von Eigenschaften, die erheblich langsamer als ein Satz von Feldern sind, nicht empfohlen.  Weitere Informationen finden Sie unter [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/de-de/55825e8f-7e2e-448a-9505-7217cc91b1af).  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 Die <xref:System.Windows.Controls.TextBlock.Text%2A>\-Eigenschaft wird mit <xref:System.Windows.Data.PriorityBinding> an den oben erwähnten `AsyncDS` gebunden:  
  
 [!code-xml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Wenn das Bindungsmodul die <xref:System.Windows.Data.Binding>\-Objekte verarbeitet, wird zunächst das erste <xref:System.Windows.Data.Binding>\-Element verarbeitet, das an die `SlowestDP`\-Eigenschaft gebunden ist.  Wenn dieses <xref:System.Windows.Data.Binding>\-Element verarbeitet wurde, gibt es keinen Wert erfolgreich zurück, da es 5 Sekunden deaktiviert ist. Deshalb wird das nächste <xref:System.Windows.Data.Binding>\-Element verarbeitet.  Das nächste <xref:System.Windows.Data.Binding>\-Element gibt keinen Wert erfolgreich zurück, da es 3 Sekunden aktiviert ist.  Das Bindungsmodul fährt mit dem nächsten <xref:System.Windows.Data.Binding>\-Element fort, das an die `FastDP`\-Eigenschaft gebunden ist.  Dieses <xref:System.Windows.Data.Binding>\-Element gibt den Wert "Fast Value" zurück.  Der <xref:System.Windows.Controls.TextBlock> zeigt jetzt den Wert "Fast Value" an.  
  
 Nach 3 Sekunden gibt die `SlowerDP`\-Eigenschaft den Wert "Slower Value" zurück.  Der <xref:System.Windows.Controls.TextBlock> zeigt dann den Wert "Slower Value" an.  
  
 Nach 5 Sekunden gibt die `SlowestDP`\-Eigenschaft den Wert "Slowest Value" zurück.  Diese Bindung hat die höchste Priorität, weil sie zuerst in der Liste angezeigt wird.  Der <xref:System.Windows.Controls.TextBlock> zeigt jetzt den Wert "Slowest Value" an.  
  
 Weitere Informationen über erfolgreiche Rückgabewerte von einer Bindung finden Sie unter <xref:System.Windows.Data.PriorityBinding>.  
  
## Siehe auch  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=fullName>   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)