---
title: 'Vorgehensweise: Überschreiben der logischen Struktur'
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768445"
---
# <a name="how-to-override-the-logical-tree"></a>Vorgehensweise: Überschreiben der logischen Struktur
Obwohl es in den meisten Fällen nicht erforderlich ist, können erfahrene Autoren von Steuerelementen in der logischen Struktur überschreiben.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird beschrieben, wie Sie die Unterklasse <xref:System.Windows.Controls.StackPanel> die logische Struktur in diesem Fall überschreiben, um ein Verhalten zu erzwingen, dass der Bereich kann nur und wird nur ein einzelnes untergeordnetes Element gerendert. Dieses Verhalten ist nicht unbedingt praktisch und erwünscht, aber es dient hier zur Veranschaulichung des Szenarios zum Überschreiben der normalen logischen Struktur eines Elements.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](trees-in-wpf.md).
