---
title: 'Gewusst wie: Erstellen eines schreibgeschützten Freezable-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460068"
---
# <a name="how-to-make-a-freezable-read-only"></a>Gewusst wie: Erstellen eines schreibgeschützten Freezable-Objekts
In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Freezable> schreibgeschützt wird, indem seine <xref:System.Windows.Freezable.Freeze%2A>-Methode aufgerufen wird.  
  
 Sie können ein <xref:System.Windows.Freezable> Objekt nicht fixieren, wenn eine der folgenden Bedingungen für das Objekt `true` ist:  
  
- Sie verfügt über animierte oder Daten gebundene Eigenschaften.  
  
- Sie verfügt über Eigenschaften, die durch eine dynamische Ressource festgelegt werden. Weitere Informationen zu dynamischen Ressourcen finden Sie in den [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Sie enthält <xref:System.Windows.Freezable> unter Objekte, die nicht eingefroren werden können.  
  
 Wenn diese Bedingungen für das <xref:System.Windows.Freezable> Objekt `false` werden und Sie es nicht ändern möchten, sollten Sie es in Erwägung nehmen, es zu erwerben, um Leistungsvorteile zu erzielen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein-<xref:System.Windows.Media.SolidColorBrush>, bei dem es sich um einen Typ von <xref:System.Windows.Freezable>-Objekt handelt, eingefroren.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Weitere Informationen zu <xref:System.Windows.Freezable> Objekten finden Sie in der [Übersicht](freezable-objects-overview.md)über frei wählbare Objekte.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Übersicht über Freezable-Objekte](freezable-objects-overview.md)
- [Themen zu Vorgehensweisen](base-elements-how-to-topics.md)
