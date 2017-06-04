---
title: "Gewusst wie: Klonen eines Druckers | Microsoft Docs"
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
  - "Klonen von Druckwarteschlangen"
  - "Klonen von Druckern"
  - "Druckwarteschlangen"
  - "Druckwarteschlangen, Klonen"
  - "Drucker, Klonen"
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Klonen eines Druckers
Die meisten Unternehmen kaufen zu einem bestimmten Zeitpunkt mehrere Drucker vom gleichen Modell.  In der Regel sind alle mit praktisch identischen Konfigurationseinstellungen installiert.  Jeden Drucker zu installieren, kann zeitaufwendig und fehleranfällig sein.  Der <xref:System.Printing.IndexedProperties?displayProperty=fullName>\-Namespace und die <xref:System.Printing.PrintServer.InstallPrintQueue%2A>\-Klasse, die mit [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)] verfügbar gemacht werden, ermöglichen die sofortige Installation einer beliebigen Zahl von zusätzlichen Druckwarteschlangen, die von einer vorhandenen Druckwarteschlange geklont werden.  
  
## Beispiel  
 Im folgenden Beispiel wird eine zweite Druckwarteschlange von einer vorhandenen Druckwarteschlange geklont.  Die zweite unterscheidet sich von der ersten nur durch ihren Namen, Standort, Anschluss und Freigabestatus.  Die wichtigsten Schritte diese Vorgehensweise sind:  
  
1.  Erstellen Sie ein <xref:System.Printing.PrintQueue>\-Objekt für den vorhandenen Drucker, der geklont wird.  
  
2.  Erstellen Sie ein <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> aus der <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> der <xref:System.Printing.PrintQueue>.  Die <xref:System.Collections.DictionaryEntry.Value%2A>\-Eigenschaft für jeden Eintrag in diesem Wörterbuch ist ein Objekt, das zu einem der von <xref:System.Printing.IndexedProperties.PrintProperty> abgeleiteten Typen gehört.  Es gibt zwei Möglichkeiten, den Wert eines Eintrags in dieses Wörterbuch festzulegen.  
  
    -   Verwenden Sie die **Remove**\-Methode und die <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A>\-Methode des Wörterbuchs, um den Eintrag zu entfernen und ihn dann mit dem gewünschten Wert wieder hinzuzufügen.  
  
    -   Verwenden Sie die <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A>\-Methode des Wörterbuchs.  
  
     Im Beispiel unten werden beide Methoden veranschaulicht.  
  
3.  Erstellen Sie ein <xref:System.Printing.IndexedProperties.PrintBooleanProperty>\-Objekt, und legen Sie <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> für das Objekt auf "IsShared" und <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> auf `true` fest.  
  
4.  Verwenden Sie das <xref:System.Printing.IndexedProperties.PrintBooleanProperty>\-Objekt als Wert des "IsShared"\-Eintrags für das <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>.  
  
5.  Erstellen Sie ein <xref:System.Printing.IndexedProperties.PrintStringProperty>\-Objekt, und legen Sie <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> für das Objekt auf "ShareName" und <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> auf einen entsprechenden <xref:System.String>\-Wert fest.  
  
6.  Verwenden Sie das <xref:System.Printing.IndexedProperties.PrintStringProperty>\-Objekt als Wert des "ShareName"\-Eintrags für das <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>.  
  
7.  Erstellen Sie ein weiteres <xref:System.Printing.IndexedProperties.PrintStringProperty>\-Objekt, und legen Sie <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> für das Objekt auf "Location" und <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> auf einen entsprechenden <xref:System.String>\-Wert fest.  
  
8.  Verwenden Sie das zweite <xref:System.Printing.IndexedProperties.PrintStringProperty>\-Objekt als Wert des "Location"\-Eintrags für das <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>.  
  
9. Erstellen Sie ein <xref:System.String>\-Array.  Jedes Element ist der Name eines Anschlusses auf dem Server.  
  
10. Verwenden Sie <xref:System.Printing.PrintServer.InstallPrintQueue%2A>, um den neuen Drucker mit den neuen Werten zu installieren.  
  
 Im Folgenden ein Beispiel.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## Siehe auch  
 <xref:System.Printing.IndexedProperties>   
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Collections.DictionaryEntry>   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Übersicht über das Drucken](../../../../docs/framework/wpf/advanced/printing-overview.md)