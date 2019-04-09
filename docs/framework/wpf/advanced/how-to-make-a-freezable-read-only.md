---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten Freezable-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 9b7102db4de0df7183355e50e3b372eac30d81b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191438"
---
# <a name="how-to-make-a-freezable-read-only"></a>Vorgehensweise: Erstellen eines schreibgeschützten Freezable-Objekts
Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.Freezable> schreibgeschützte durch Aufrufen der <xref:System.Windows.Freezable.Freeze%2A> Methode.  
  
 Sie können nicht eingefroren werden eine <xref:System.Windows.Freezable> Objekt, wenn eine der folgenden Bedingungen ist `true` über das Objekt:  
  
-   Es verfügt über animierte oder datengebundene Eigenschaften.  
  
-   Es verfügt über Eigenschaften, die von einer dynamischen Ressource festgelegt werden. Weitere Informationen zu dynamischen Ressourcen finden Sie unter den [XAML-Ressourcen](xaml-resources.md).  
  
-   Es enthält <xref:System.Windows.Freezable> untergeordnete Objekte, die nicht fixiert werden können.  
  
 Wenn diese Bedingungen sind `false` für Ihre <xref:System.Windows.Freezable> -Objekt, und Sie beabsichtigen nicht, es ändern möchten, sollten das fixieren, um Leistungsvorteile zu erhalten.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel friert ein <xref:System.Windows.Media.SolidColorBrush>, ist ein Typ, der <xref:System.Windows.Freezable> Objekt.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Weitere Informationen zu <xref:System.Windows.Freezable> Objekten finden Sie die [Übersicht über Freezable-Objekte](freezable-objects-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [Übersicht über Freezable-Objekte](freezable-objects-overview.md)
- [Gewusst wie-Themen](base-elements-how-to-topics.md)
