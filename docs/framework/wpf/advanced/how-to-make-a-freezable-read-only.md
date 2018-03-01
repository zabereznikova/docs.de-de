---
title: "Gewusst wie: Erstellen eines schreibgeschützten Freezable-Objekts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa6d3f7109e8258dff0a07556bc8572f6071c961
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-a-freezable-read-only"></a>Gewusst wie: Erstellen eines schreibgeschützten Freezable-Objekts
Dieses Beispiel zeigt, wie Sie eine <xref:System.Windows.Freezable> schreibgeschützt sind und durch Aufrufen seiner <xref:System.Windows.Freezable.Freeze%2A> Methode.  
  
 Sie können nicht eingefroren werden eine <xref:System.Windows.Freezable> Objekt, wenn eine der folgenden Bedingungen ist `true` über das Objekt:  
  
-   Es verfügt über animierte oder datengebundene Eigenschaften.  
  
-   Sie verfügt über Eigenschaften, die von einer dynamischen Ressource festgelegt werden. Weitere Informationen zu dynamischen Ressourcen finden Sie unter der [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Er enthält <xref:System.Windows.Freezable> untergeordnete Objekte, die nicht fixiert werden können.  
  
 Wenn diese Bedingungen sind `false` für Ihre <xref:System.Windows.Freezable> -Objekt, und Sie möchten nicht ändern, sollten die Sperren, um die Leistungsvorteile zu erhalten.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel werden eingefroren eine <xref:System.Windows.Media.SolidColorBrush>, d. h. einen Typ von <xref:System.Windows.Freezable> Objekt.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Weitere Informationen zu <xref:System.Windows.Freezable> anzuzeigen, die [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
