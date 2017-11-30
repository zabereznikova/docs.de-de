---
title: "Gewusst wie: Überschreiben der logischen Struktur"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6045d3505981d93f07347ebd49d57cd759774
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-override-the-logical-tree"></a>Gewusst wie: Überschreiben der logischen Struktur
Obwohl es in den meisten Fällen nicht erforderlich ist, können erfahrene Autoren von Steuerelementen in der logischen Struktur überschreiben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird beschrieben, wie Sie Unterklasse <xref:System.Windows.Controls.StackPanel> die logische Struktur in diesem Fall überschreiben, um ein Verhalten zu erzwingen, dass der Bereich nur enthalten sein darf und wird nur ein einzelnes untergeordnetes Element gerendert. Dieses Verhalten ist nicht unbedingt praktisch und erwünscht, aber es dient hier zur Veranschaulichung des Szenarios zum Überschreiben der normalen logischen Struktur eines Elements.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).
