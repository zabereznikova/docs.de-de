---
title: "Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Datenbindung, MultiBinding"
  - "MultiBinding"
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Erzeugen eines Werts auf Grundlage einer Liste gebundener Elemente
Mit <xref:System.Windows.Data.MultiBinding> können Sie eine Eigenschaft eines [Bindungsziels](GTMT) an eine Liste von Quelleigenschaften binden und anschließend Logik anwenden, um einen Wert mit den angegebenen Eingaben zu erstellen.  In diesem Beispiel wird die Verwendung von <xref:System.Windows.Data.MultiBinding> veranschaulicht.  
  
## Beispiel  
 Im folgenden Beispiel verweist `NameListData` auf eine Auflistung von `PersonName`\-Objekten, bei denen es sich um Objekte handelt, die zwei Eigenschaften enthalten, `firstName` und `lastName`.  Im folgenden Beispiel wird ein Wert für <xref:System.Windows.Controls.TextBlock> erzeugt, der Vorname und Nachname einer Person anzeigt. Dabei wird der Nachname zuerst angezeigt.  
  
 [!code-xml[MultiBinding#Resources1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xml[MultiBinding#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xml[MultiBinding#MultiBindingTextBox2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xml[MultiBinding#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 Um zu verstehen, wie das Format erzeugt wird, in dem der Nachname zuerst angezeigt wird, betrachten Sie zunächst die Implementierung von `NameConverter`:  
  
 [!code-csharp[MultiBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 `NameConverter` implementiert die <xref:System.Windows.Data.IMultiValueConverter>\-Schnittstelle.  `NameConverter` übernimmt die Werte aus den einzelnen Bindungen und speichert sie im Werteobjektarray.  Die Reihenfolge, in der die <xref:System.Windows.Data.Binding>\-Elemente unter dem <xref:System.Windows.Data.MultiBinding>\-Element angezeigt werden, entspricht der Reihenfolge, in der diese Werte im Array gespeichert sind.  Auf den Wert des <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A>\-Attributs wird vom Parameterargument der <xref:System.Windows.Data.MultiBinding.Converter%2A>\-Methode verwiesen, die den Parameter umschaltet, um zu bestimmen, wie der Name formatiert wird.  
  
## Siehe auch  
 [Konvertieren von gebundenen Daten](../../../../docs/framework/wpf/data/how-to-convert-bound-data.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)