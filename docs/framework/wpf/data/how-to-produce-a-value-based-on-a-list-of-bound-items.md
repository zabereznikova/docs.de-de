---
title: 'Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente'
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
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d16a198ed78c1ffd9dcaad595e9cc9be3cb2de0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente
<xref:System.Windows.Data.MultiBinding>können Sie eine Bindungsziel-Eigenschaft auf eine Liste von Eigenschaften der Datenquelle zu binden und dann Logik anwenden, um einen Wert mit den angegebenen Eingaben zu erzeugen. In diesem Beispiel wird veranschaulicht, wie <xref:System.Windows.Data.MultiBinding>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel verweist `NameListData` auf eine Auflistung von `PersonName`-Objekten, bei denen es sich um Objekte handelt, die zwei Eigenschaften enthalten, `firstName` und `lastName`. Im folgenden Beispiel wird eine <xref:System.Windows.Controls.TextBlock> , die vor- und Nachnamen Namen einer Person mit den Nachnamen des ersten anzeigt.  
  
 [!code-xaml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Um zu verstehen, wie das Format „Nachname-Vorname“ erzeugt wird, betrachten Sie zunächst die Implementierung von `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` implementiert die <xref:System.Windows.Data.IMultiValueConverter>-Schnittstelle. `NameConverter` übernimmt die Werte aus den einzelnen Bindungen und speichert sie im Werteobjektarray. In welcher Reihenfolge die <xref:System.Windows.Data.Binding> Elemente angezeigt werden, unter der <xref:System.Windows.Data.MultiBinding> Element ist die Reihenfolge, in denen diese Werte im Array gespeichert werden. Der Wert des der <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> Parameterargument Attribut verweist die <xref:System.Windows.Data.MultiBinding.Converter%2A> Methode, die einen Switch für den Parameter, um zu bestimmen, wie der Name formatiert ausführt.  
  
## <a name="see-also"></a>Siehe auch  
 [Konvertieren von gebundenen Daten](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
