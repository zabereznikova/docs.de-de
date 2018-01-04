---
title: 'Gewusst wie: Klonen eines Druckers'
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
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43a08faf27186bde85dd12f027034f759378debf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-clone-a-printer"></a>Gewusst wie: Klonen eines Druckers
Die meisten Unternehmen werden, zu einem späteren Zeitpunkt mehrere Drucker desselben Modells kaufen. In der Regel sind diese alle mit nahezu identischen Konfigurationseinstellungen installiert. Installieren alle Drucker kann zeitaufwändig sein und fehleranfällig. Die <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> Namespace und die <xref:System.Printing.PrintServer.InstallPrintQueue%2A> -Klasse, die mit verfügbar gemacht werden [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] ermöglicht es sofort aus einer vorhandenen Druckwarteschlange installieren eine beliebige Anzahl von zusätzlichen Druckwarteschlangen, die geklont werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine zweite Druckerwarteschlange von einer vorhandenen Druckwarteschlange geklont. Die zweite unterscheidet sich von der ersten nur in dessen Namen, Speicherort, Port und freigegebenen Status. Die wichtigsten Schritte für diese Vorgehensweise sind wie folgt aus.  
  
1.  Erstellen einer <xref:System.Printing.PrintQueue> Objekt für den vorhandenen Drucker, die geklont werden soll.  
  
2.  Erstellen einer <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus der <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> von der <xref:System.Printing.PrintQueue>. Die <xref:System.Collections.DictionaryEntry.Value%2A> für jeden Eintrag in dieses Wörterbuch aufweist und ein Objekt ist eines von abgeleiteten Typen <xref:System.Printing.IndexedProperties.PrintProperty>. Es gibt zwei Möglichkeiten, den Wert eines Eintrags in diesem Wörterbuch festzulegen.  
  
    -   Das Wörterbuch zu verwenden **entfernen** und <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> Methoden zu entfernen Sie den Eintrag, und klicken Sie dann erneut mit dem gewünschten Wert hinzuzufügen.  
  
    -   Das Wörterbuch zu verwenden <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> Methode.  
  
     Das folgende Beispiel veranschaulicht beide Möglichkeiten.  
  
3.  Erstellen einer <xref:System.Printing.IndexedProperties.PrintBooleanProperty> Objekt, und seine <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> auf "IsShared" und die zugehörige <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> auf `true`.  
  
4.  Verwenden der <xref:System.Printing.IndexedProperties.PrintBooleanProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>der Eintrag "IsShared".  
  
5.  Erstellen einer <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, und seine <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> auf "ShareName" und die zugehörige <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> in eine entsprechende <xref:System.String>.  
  
6.  Verwenden der <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>der Eintrag "ShareName".  
  
7.  Erstellen Sie ein weiteres <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, und seine <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> zu "Location" und die zugehörige <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> in eine entsprechende <xref:System.String>.  
  
8.  Verwenden Sie das zweite <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>des "Location" Posten.  
  
9. Erstellt ein Array von <xref:System.String>s. Jedes Element ist der Name eines Ports auf dem Server.  
  
10. Verwendung <xref:System.Printing.PrintServer.InstallPrintQueue%2A> So installieren Sie den neuen Drucker mit den neuen Werten.  
  
 Ein Beispiel ist unten.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)
