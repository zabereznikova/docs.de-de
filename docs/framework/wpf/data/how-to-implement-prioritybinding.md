---
title: 'Vorgehensweise: Implementieren einer PriorityBinding-Klasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: ad19db9d686469e3ade1ff188553fceb8d525674
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937447"
---
# <a name="how-to-implement-prioritybinding"></a>Vorgehensweise: Implementieren einer PriorityBinding-Klasse
<xref:System.Windows.Data.PriorityBinding>in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funktioniert durch Angeben einer Liste von Bindungen. Die Liste der Bindungen ist von der höchsten Priorität bis zur niedrigsten Priorität geordnet. Wenn die Bindung mit der höchsten Priorität bei der Verarbeitung einen Wert erfolgreich zurückgibt, ist es nicht erforderlich, die anderen Bindungen in der Liste zu verarbeiten. Dies könnte der Fall sein, wenn die Bewertung mit der höchsten Priorität lange ausgewertet werden muss, wenn die nächsthöhere Priorität, die erfolgreich einen Wert zurückgibt, verwendet wird, bis eine Bindung einer höheren Priorität erfolgreich einen Wert zurückgibt.  
  
## <a name="example"></a>Beispiel  
 Um zu veranschaulichen <xref:System.Windows.Data.PriorityBinding> , wie funktioniert `AsyncDataSource` , wurde das-Objekt mit den folgenden drei Eigenschaften `FastDP`erstellt `SlowerDP`:, `SlowestDP`und.  
  
 Der Get-Accessor `FastDP` von gibt den Wert `_fastDP` des Datenmembers zurück.  
  
 Der Get-Accessor `SlowerDP` von wartet drei Sekunden, bevor er den Wert `_slowerDP` des Datenmembers zurückgibt.  
  
 Der Get-Accessor `SlowestDP` von wartet 5 Sekunden, bevor er den Wert `_slowestDP` des Datenmembers zurückgibt.  
  
> [!NOTE]
> Das Beispiel dient nur der Veranschaulichung. Die [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] Richtlinien werden zum Definieren von Eigenschaften empfohlen, die in der Größenordnung langsamer als ein Feld Satz sind. Weitere Informationen finden Sie unter [auswählen zwischen Eigenschaften und Methoden](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 Die <xref:System.Windows.Controls.TextBlock.Text%2A> -Eigenschaft bindet an die `AsyncDS` oben <xref:System.Windows.Data.PriorityBinding>genannte mithilfe von:  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Wenn die Bindungs-Engine die <xref:System.Windows.Data.Binding> -Objekte verarbeitet, beginnt Sie mit <xref:System.Windows.Data.Binding>dem ersten, das an die `SlowestDP` -Eigenschaft gebunden ist. Wenn dies <xref:System.Windows.Data.Binding> verarbeitet wird, wird ein Wert nicht erfolgreich zurückgegeben, da er 5 Sekunden lang im Ruhezustand ist, <xref:System.Windows.Data.Binding> sodass das nächste Element verarbeitet wird. Der nächste <xref:System.Windows.Data.Binding> gibt einen Wert nicht erfolgreich zurück, da er drei Sekunden lang im Ruhezustand ist. Die Bindungs-Engine wechselt dann auf das <xref:System.Windows.Data.Binding> nächste Element, das an die `FastDP` -Eigenschaft gebunden ist. Dadurch <xref:System.Windows.Data.Binding> wird der Wert "fast Value" zurückgegeben. Der <xref:System.Windows.Controls.TextBlock> zeigt jetzt den Wert "schneller Wert" an.  
  
 Nach 3 Sekunden gibt die `SlowerDP` -Eigenschaft den Wert "langsamerer Wert" zurück. Der <xref:System.Windows.Controls.TextBlock> zeigt dann den Wert "langsamerer Wert" an.  
  
 Nach 5 Sekunden gibt die `SlowestDP` -Eigenschaft den Wert "Slowest Value" zurück. Diese Bindung hat die höchste Priorität, da Sie zuerst aufgeführt wird. Der <xref:System.Windows.Controls.TextBlock> zeigt jetzt den Wert "Langsamster Wert" an.  
  
 Informationen <xref:System.Windows.Data.PriorityBinding> dazu, was als erfolgreicher Rückgabewert einer Bindung angesehen wird, finden Sie unter.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
