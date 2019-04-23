---
title: 'Vorgehensweise: Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: afecb87dcfce1a8c48f1b2108edeae3cfd2aa16f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209657"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>Vorgehensweise: Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse
In diesem Beispiel wird veranschaulicht, wie XML-Daten binden ein <xref:System.Windows.Controls.ItemsControl> mit <xref:System.Xml.Linq.XDocument>.  
  
## <a name="example"></a>Beispiel  
 Der folgende XAML-Code definiert eine <xref:System.Windows.Controls.ItemsControl> und schließt eine Datenvorlage für Daten vom Typ `Planet` in die `http://planetsNS` XML-Namespace. Ein XML-Datentyp, der in einem Namespace definiert ist, muss den Namespace in geschweiften Klammern enthalten. An einer Position, an der XAML-Markuperweiterungen auftreten können, muss dem Namespace eine Escapesequenz mit geschweiften Klammern vorangestellt werden. Dieser Code bindet an dynamische Eigenschaften entsprechen den <xref:System.Xml.Linq.XContainer.Element%2A> und <xref:System.Xml.Linq.XElement.Attribute%2A> Methoden der <xref:System.Xml.Linq.XElement> Klasse. Dynamische Eigenschaften ermöglichen die Bindung von XAML an dynamische Eigenschaften, die die Namen von Methoden gemeinsam verwenden. Weitere Informationen dazu finden Sie unter [Dynamische Eigenschaften in LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties). Beachten Sie, dass die XML-Standardnamespacedeklaration nicht für Attributnamen gilt.  
  
 [!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 Der folgende C#-Code ruft <xref:System.Xml.Linq.XDocument.Load%2A> und legt den StackPanel-Datenkontext auf alle Unterelemente des Elements namens `SolarSystemPlanets` in die `http://planetsNS` XML-Namespace.  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 XML-Daten gespeichert werden können, als eine XAML-Ressourcen mit <xref:System.Windows.Data.ObjectDataProvider>. Ein vollständiges Beispiel finden Sie unter [L2DBForm.xaml-Quellcode](/visualstudio/designers/l2dbform-xaml-source-code). Im folgenden Beispiel wird gezeigt, wie der Datenkontext in Code auf eine Objektressource festgelegt werden kann.  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 Die dynamischen Eigenschaften, die den zuordnen <xref:System.Xml.Linq.XContainer.Element%2A> und <xref:System.Xml.Linq.XElement.Attribute%2A> sorgen für Flexibilität in XAML. Der Code kann auch an die Ergebnisse einer LINQ to XML-Abfrage gebunden werden. In diesem Beispiel erfolgt die Bindung an die nach einem Elementwert sortierten Abfrageergebnisse.  
  
 [!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Bindungsquellen](binding-sources-overview.md)
- [Übersicht über WPF-Datenbindung mit LINQ to XML](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)
- [Beispiel für die WPF-Datenbindung mit LINQ to XML](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)
- [Dynamische Eigenschaften in LINQ to XML](/visualstudio/designers/linq-to-xml-dynamic-properties)
