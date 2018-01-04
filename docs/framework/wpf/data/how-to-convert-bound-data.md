---
title: 'Gewusst wie: Konvertieren von gebundenen Daten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f4bcde15940e76e1d022658e32ff6ef8676e45e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-convert-bound-data"></a>Gewusst wie: Konvertieren von gebundenen Daten
Dieses Beispiel zeigt, wie die Konvertierung in Daten angewendet, die in Bindungen verwendet wird.  
  
 Um Daten während der Bindung zu konvertieren, müssen Sie eine Klasse, die implementiert erstellen die <xref:System.Windows.Data.IValueConverter> -Schnittstelle, die umfasst die <xref:System.Windows.Data.IValueConverter.Convert%2A> und <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> Methoden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Implementierung für einen Datum-Konverter, der den Date-Wert übergeben, damit das Jahr, Monat und Tag nur zeigt konvertiert. Bei der Implementierung der <xref:System.Windows.Data.IValueConverter> -Schnittstelle, es wird empfohlen, ergänzen die Implementierung mit einem <xref:System.Windows.Data.ValueConversionAttribute> Attribut an, dass für die Entwicklung tools die Datentypen bei der Konvertierung, wie im folgenden Beispiel:  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Nachdem Sie einen Konverter erstellt haben, können Sie ihn hinzufügen, als Ressource in Ihre [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Datei. Im folgenden Beispiel *Src* ordnet den Namespace, in dem *DateConverter* definiert ist.  
  
 [!code-xaml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Schließlich können Sie den Konverter in der Bindung mithilfe der folgenden Syntax verwenden. Im folgenden Beispiel werden die von der Textinhalt der <xref:System.Windows.Controls.TextBlock> gebunden ist *"StartDate"*, also eine Eigenschaft einer externen Datenquelle.  
  
 [!code-xaml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Die Style-Ressourcen, die im obigen Beispiel verwiesen werden in einem Ressourcenabschnitt nicht angezeigt, in diesem Thema definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Implementieren der Bindungsvalidierung](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
