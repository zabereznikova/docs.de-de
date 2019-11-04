---
title: 'Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: da183a34eb85de54b1e3f54f8d14c09e25640165
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459691"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a>Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente
mit <xref:System.Windows.Data.MultiBinding> können Sie eine Bindungs Ziel Eigenschaft an eine Liste von Quell Eigenschaften binden und dann die Logik anwenden, um einen Wert mit den angegebenen Eingaben zu erhalten. In diesem Beispiel wird die Verwendung <xref:System.Windows.Data.MultiBinding>veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel verweist `NameListData` auf eine Auflistung von `PersonName`-Objekten, bei denen es sich um Objekte handelt, die zwei Eigenschaften enthalten, `firstName` und `lastName`. Im folgenden Beispiel wird eine <xref:System.Windows.Controls.TextBlock> erstellt, die zuerst den vor-und Nachnamen einer Person mit dem Nachnamen anzeigt.  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Um zu verstehen, wie das Format „Nachname-Vorname“ erzeugt wird, betrachten Sie zunächst die Implementierung von `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` implementiert die <xref:System.Windows.Data.IMultiValueConverter>-Schnittstelle. `NameConverter` übernimmt die Werte aus den einzelnen Bindungen und speichert sie im Werteobjektarray. Die Reihenfolge, in der die <xref:System.Windows.Data.Binding> Elemente unter dem <xref:System.Windows.Data.MultiBinding>-Element angezeigt werden, ist die Reihenfolge, in der diese Werte im Array gespeichert werden. Auf den Wert des <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> Attributs wird durch das Parameter-Argument der <xref:System.Windows.Data.MultiBinding.Converter%2A>-Methode verwiesen, die einen Schalter für den-Parameter ausführt, um zu bestimmen, wie der Name formatiert werden soll.  
  
## <a name="see-also"></a>Siehe auch

- [Konvertieren von gebundenen Daten](how-to-convert-bound-data.md)
- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
