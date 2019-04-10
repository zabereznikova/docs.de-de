---
title: 'Vorgehensweise: Klonen eines Druckers'
ms.date: 03/30/2017
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
ms.openlocfilehash: 09a445da068f0141b9526e0228df8be0105498c6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310459"
---
# <a name="how-to-clone-a-printer"></a>Vorgehensweise: Klonen eines Druckers
Die meisten Unternehmen werden irgendwann mehrere Drucker desselben Modells erwerben. Diese werden alle in der Regel mit nahezu identischen Konfigurationseinstellungen installiert. Installieren die einzelnen Drucker kann sehr zeitaufwändig sein und fehleranfällig. Die <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> Namespace und die <xref:System.Printing.PrintServer.InstallPrintQueue%2A> -Klasse, die mit Microsoft .NET Framework verfügbar gemacht werden ermöglicht, eine beliebige Anzahl von zusätzlichen Druckwarteschlangen, die geklont werden sofort aus einer vorhandenen Druckwarteschlange zu installieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine zweite Druckwarteschlange aus einer vorhandenen Druckwarteschlange geklont. Die zweite, die von der ersten unterscheidet sich nur in dessen Namen, Speicherort, Port und freigegebenen Status. Die wichtigsten Schritte dazu sind wie folgt aus.  
  
1. Erstellen Sie eine <xref:System.Printing.PrintQueue> Objekt für den vorhandenen Drucker, die geklont werden.  
  
2. Erstellen Sie eine <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus der <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> von der <xref:System.Printing.PrintQueue>. Die <xref:System.Collections.DictionaryEntry.Value%2A> -Eigenschaft für jeden Eintrag in diesem Wörterbuch ist ein Objekt vom Typ abgeleitet <xref:System.Printing.IndexedProperties.PrintProperty>. Es gibt zwei Möglichkeiten, den Wert eines Eintrags in dieses Wörterbuch festlegen.  
  
    -   Verwenden des Wörterbuchs **entfernen** und <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> Methoden entfernen Sie den Eintrag, und klicken Sie dann erneut mit dem gewünschten Wert hinzufügen.  
  
    -   Verwenden des Wörterbuchs <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> Methode.  
  
     Das folgende Beispiel veranschaulicht beide Möglichkeiten.  
  
3. Erstellen einer <xref:System.Printing.IndexedProperties.PrintBooleanProperty> Objekt, und legen dessen <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> auf "IsShared" und die zugehörige <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> zu `true`.  
  
4. Verwenden der <xref:System.Printing.IndexedProperties.PrintBooleanProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>des "IsShared"-Eintrag.  
  
5. Erstellen einer <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, und legen dessen <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> auf "ShareName" und die zugehörige <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> auf einen entsprechenden <xref:System.String>.  
  
6. Verwenden der <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>des "Freigabename"-Eintrag.  
  
7. Erstellen Sie eine weitere <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, und legen dessen <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> , "Location" und die zugehörige <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> auf einen entsprechenden <xref:System.String>.  
  
8. Im zweiten <xref:System.Printing.IndexedProperties.PrintStringProperty> Objekt, das der Wert der <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>die "Location"-Eintrag.  
  
9. Erstellt ein Array von <xref:System.String>s. Jedes Element ist der Name eines Ports auf dem Server.  
  
10. Verwendung <xref:System.Printing.PrintServer.InstallPrintQueue%2A> So installieren Sie den neuen Drucker mit den neuen Werten.  
  
 Ein Beispiel ist unten.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
