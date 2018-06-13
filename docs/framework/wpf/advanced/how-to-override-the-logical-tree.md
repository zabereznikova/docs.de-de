---
title: 'Gewusst wie: Überschreiben der logischen Struktur'
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: 0c7269b9ea052019e2e4f6def23b063903cbb5e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542889"
---
# <a name="how-to-override-the-logical-tree"></a>Gewusst wie: Überschreiben der logischen Struktur
Obwohl es in den meisten Fällen nicht erforderlich ist, können erfahrene Autoren von Steuerelementen in der logischen Struktur überschreiben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird beschrieben, wie Sie Unterklasse <xref:System.Windows.Controls.StackPanel> die logische Struktur in diesem Fall überschreiben, um ein Verhalten zu erzwingen, dass der Bereich nur enthalten sein darf und wird nur ein einzelnes untergeordnetes Element gerendert. Dieses Verhalten ist nicht unbedingt praktisch und erwünscht, aber es dient hier zur Veranschaulichung des Szenarios zum Überschreiben der normalen logischen Struktur eines Elements.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).
