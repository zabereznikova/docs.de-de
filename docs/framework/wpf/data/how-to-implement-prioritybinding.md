---
title: 'Gewusst wie: Implementieren von PriorityBinding'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 343b0aca4736905f3a0cbff5a0f76b170da0c920
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459779"
---
# <a name="how-to-implement-prioritybinding"></a>Gewusst wie: Implementieren von PriorityBinding
<xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funktioniert, indem eine Liste von Bindungen angegeben wird. Die Liste der Bindungen ist von der höchsten Priorität bis zur niedrigsten Priorität geordnet. Wenn die Bindung mit der höchsten Priorität bei der Verarbeitung einen Wert erfolgreich zurückgibt, ist es nicht erforderlich, die anderen Bindungen in der Liste zu verarbeiten. Dies könnte der Fall sein, wenn die Bewertung mit der höchsten Priorität lange ausgewertet werden muss, wenn die nächsthöhere Priorität, die erfolgreich einen Wert zurückgibt, verwendet wird, bis eine Bindung einer höheren Priorität erfolgreich einen Wert zurückgibt.  
  
## <a name="example"></a>Beispiel  
 Um zu veranschaulichen, wie <xref:System.Windows.Data.PriorityBinding> funktioniert, wurde das `AsyncDataSource`-Objekt mit den folgenden drei Eigenschaften erstellt: `FastDP`, `SlowerDP`und `SlowestDP`.  
  
 Der Get-Accessor von `FastDP` gibt den Wert des `_fastDP` Datenmembers zurück.  
  
 Der Get-Accessor von `SlowerDP` wartet drei Sekunden, bevor er den Wert des `_slowerDP` Datenmembers zurückgibt.  
  
 Der Get-Accessor von `SlowestDP` wartet 5 Sekunden, bevor er den Wert des `_slowestDP` Datenmembers zurückgibt.  
  
> [!NOTE]
> Das Beispiel dient nur der Veranschaulichung. Die .NET-Richtlinien werden zum Definieren von Eigenschaften empfohlen, die in der Größenordnung langsamer sind als ein Feld Satz. Weitere Informationen finden Sie unter [auswählen zwischen Eigenschaften und Methoden](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 Die <xref:System.Windows.Controls.TextBlock.Text%2A>-Eigenschaft wird mithilfe <xref:System.Windows.Data.PriorityBinding>an die oben genannte `AsyncDS` gebunden:  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 Wenn die Bindungs-Engine die <xref:System.Windows.Data.Binding> Objekte verarbeitet, beginnt Sie mit dem ersten <xref:System.Windows.Data.Binding>, das an die `SlowestDP`-Eigenschaft gebunden ist. Wenn diese <xref:System.Windows.Data.Binding> verarbeitet wird, wird ein Wert nicht erfolgreich zurückgegeben, da er 5 Sekunden lang im Ruhezustand ist, sodass das nächste <xref:System.Windows.Data.Binding> Element verarbeitet wird. Der nächste <xref:System.Windows.Data.Binding> gibt einen Wert nicht erfolgreich zurück, da er drei Sekunden lang im Ruhezustand ist. Die Bindungs-Engine wechselt dann zum nächsten <xref:System.Windows.Data.Binding>-Element, das an die `FastDP`-Eigenschaft gebunden ist. Diese <xref:System.Windows.Data.Binding> gibt den Wert "fast Value" zurück. Die <xref:System.Windows.Controls.TextBlock> zeigt jetzt den Wert "schneller Wert" an.  
  
 Nach 3 Sekunden gibt die `SlowerDP`-Eigenschaft den Wert "langsamerer Wert" zurück. Der <xref:System.Windows.Controls.TextBlock> zeigt dann den Wert "langsamerer Wert" an.  
  
 Nach 5 Sekunden gibt die `SlowestDP`-Eigenschaft den Wert "Langsamster Wert" zurück. Diese Bindung hat die höchste Priorität, da Sie zuerst aufgeführt wird. Die <xref:System.Windows.Controls.TextBlock> zeigt jetzt den Wert "Langsamster Wert" an.  
  
 Informationen dazu, was als erfolgreicher Rückgabewert einer Bindung angesehen wird, finden Sie unter <xref:System.Windows.Data.PriorityBinding>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
