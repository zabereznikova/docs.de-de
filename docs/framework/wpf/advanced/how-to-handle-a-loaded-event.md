---
title: 'Vorgehensweise: Behandeln eines geladenen Ereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: a4916d3cfd20d082a8466f61fc74e16db2f0f346
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353347"
---
# <a name="how-to-handle-a-loaded-event"></a>Vorgehensweise: Behandeln eines geladenen Ereignisses
Dieses Beispiel zeigt, wie behandelt die <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> Ereignis und einem entsprechenden Szenario für die Behandlung dieses Ereignisses. Der Ereignishandler erstellt ein <xref:System.Windows.Controls.Button> beim Laden der Seite.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zusammen mit einem Code-Behind-Datei.  
  
 [!code-xaml[FELoaded#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.FrameworkElement>
- [Objektlebensdauer-Ereignisse](object-lifetime-events.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
- [Themen zu Vorgehensweisen](base-elements-how-to-topics.md)
