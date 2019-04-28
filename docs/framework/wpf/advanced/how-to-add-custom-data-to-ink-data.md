---
title: 'Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu Freihanddaten'
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: c524e30943a21426e2e5e8fe6ae009999924fead
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777051"
---
# <a name="how-to-add-custom-data-to-ink-data"></a>Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu Freihanddaten
Sie können Freihand benutzerdefinierte Daten hinzufügen, die beim Speichern der Freihandeingabe als serialisierte Freihandeingabe-Format (ISF) gespeichert werden.  Sie können die benutzerdefinierten Daten zu speichern die <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, oder die <xref:System.Windows.Ink.Stroke>.  Wird zum Speichern von benutzerdefinierter Daten für drei Objekte können Ihnen die Möglichkeit der beste Ort zum Speichern der Daten zu entscheiden.  Alle drei Klassen verwenden ähnliche Methoden zum Speichern und auf benutzerdefinierte Daten zugreifen.  
  
 Nur die folgenden Typen können als benutzerdefinierte Daten gespeichert werden:  
  
- <xref:System.Boolean>  
  
- <xref:System.Boolean>[]  
  
- <xref:System.Byte>  
  
- <xref:System.Byte>[]  
  
- <xref:System.Char>  
  
- <xref:System.Char>[]  
  
- <xref:System.DateTime>  
  
- <xref:System.DateTime>[]  
  
- <xref:System.Decimal>  
  
- <xref:System.Decimal>[]  
  
- <xref:System.Double>  
  
- <xref:System.Double>[]  
  
- <xref:System.Int16>  
  
- <xref:System.Int16>[]  
  
- <xref:System.Int32>  
  
- <xref:System.Int32>[]  
  
- <xref:System.Int64>  
  
- <xref:System.Int64>[]  
  
- <xref:System.Single>  
  
- <xref:System.Single>[]  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <xref:System.UInt16>[]  
  
- <xref:System.UInt32>  
  
- <xref:System.UInt32>[]  
  
- <xref:System.UInt64>  
  
- <xref:System.UInt64>[]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Hinzufügen und Abrufen von benutzerdefinierten Daten aus einer <xref:System.Windows.Ink.StrokeCollection>.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 Das folgende Beispiel erstellt eine Anwendung, die zeigt eine <xref:System.Windows.Controls.InkCanvas> und zwei Schaltflächen.  Die Schaltfläche `switchAuthor`, zwei Stifte, die von zwei verschiedenen Autoren verwendet werden können.  Die Schaltfläche mit den `changePenColors` ändert sich die Farbe der einzelnen Striche auf der <xref:System.Windows.Controls.InkCanvas> gemäß der Autor.  Die Anwendung definiert zwei <xref:System.Windows.Ink.DrawingAttributes> -Objekte und fügt eine benutzerdefinierte Eigenschaft, der angibt, welche Autor gezeichnet wurde jeweils der <xref:System.Windows.Ink.Stroke>.  Wenn der Benutzer klickt `changePenColors`, die Anwendung ändert die Darstellung des Strichs entsprechend dem Wert der benutzerdefinierten Eigenschaft.  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
