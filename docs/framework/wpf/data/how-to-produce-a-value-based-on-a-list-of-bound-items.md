---
title: 'Vorgehensweise: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: c2ec5ff26c89649294df266e790445e5aa5d08ae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200518"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Vorgehensweise: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente
<xref:System.Windows.Data.MultiBinding> können Sie eine Eigenschaft eines Bindungsziels an eine Liste von Quelleigenschaften binden und anschließend Logik anwenden, um einen Wert mit den angegebenen Eingaben zu erzeugen. In diesem Beispiel wird veranschaulicht, wie <xref:System.Windows.Data.MultiBinding>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel verweist `NameListData` auf eine Auflistung von `PersonName`-Objekten, bei denen es sich um Objekte handelt, die zwei Eigenschaften enthalten, `firstName` und `lastName`. Im folgenden Beispiel wird eine <xref:System.Windows.Controls.TextBlock> , die die ersten und letzten Namen einer Person mit dem Nachnamen ersten zeigt.  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Um zu verstehen, wie das Format „Nachname-Vorname“ erzeugt wird, betrachten Sie zunächst die Implementierung von `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` implementiert die <xref:System.Windows.Data.IMultiValueConverter>-Schnittstelle. `NameConverter` übernimmt die Werte aus den einzelnen Bindungen und speichert sie im Werteobjektarray. Die Reihenfolge, in der <xref:System.Windows.Data.Binding> Elemente angezeigt werden, unter der <xref:System.Windows.Data.MultiBinding> Element ist die Reihenfolge, in dem diese Werte im Array gespeichert sind. Der Wert des der <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> Parameterargument Attribut verweist die <xref:System.Windows.Data.MultiBinding.Converter%2A> -Methode, die mit einen Switch für den Parameter, um zu bestimmen, wie der Name formatiert ausführt.  
  
## <a name="see-also"></a>Siehe auch

- [Konvertieren von gebundenen Daten](how-to-convert-bound-data.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
