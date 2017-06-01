---
title: "Gewusst wie: &#220;berschreiben der logischen Struktur | Microsoft Docs"
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
  - "Logische Struktur, Überschreiben"
  - "Überschreiben der logischen Struktur"
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: &#220;berschreiben der logischen Struktur
Erfahrene Autoren von Steuerelementen können die [logische Struktur](GTMT) überschreiben, auch wenn dies in den meisten Fällen nicht erforderlich ist.  
  
## Beispiel  
 In diesem Beispiel wird erläutert, wie Unterklassen des <xref:System.Windows.Controls.StackPanel> gebildet werden, um die logische Struktur zu überschreiben. In diesem Fall wird ein spezielles Verhalten des Bereichs erzwungen, und es wird ein einzelnes untergeordnetes Element gerendert.  Dieses Verhalten ist in der Praxis nicht wirklich wünschenswert. Es wird hier lediglich verwendet, um das Szenario für die Überschreibung der gewohnten logischen Struktur eines Elements zu veranschaulichen.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).