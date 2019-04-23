---
title: Daten und Datenobjekte
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data transfer [WPF], drag-and-drop
- DataFormats class [WPF]
- DataObject class [WPF]
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
ms.openlocfilehash: 9dc195ece60739cf0c137a2893c9e9150e0d4d3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312058"
---
# <a name="data-and-data-objects"></a>Daten und Datenobjekte
Als Teil eines Drag & Drop-Vorgangs übertragenen Daten werden in einem Datenobjekt gespeichert.  Konzeptionell besteht aus einem Datenobjekt eine oder mehrere der folgenden Paare:  
  
-   Ein <xref:System.Object> , die die eigentlichen Daten enthält.  
  
-   Einem entsprechenden Datenformatbezeichner.  
  
 Die Daten selbst können alle Elemente, die als Basis dargestellt werden können bestehen <xref:System.Object>.  Das entsprechende Datenformat ist eine Zeichenfolge oder <xref:System.Type> , der ein Hinweis zum format der Daten ist bereitstellt.  Datenobjekte unterstützen mehrere Daten/Format Paare hosten kann. Dies ermöglicht ein einzelnen Datenobjekt Daten in mehreren Formaten bereitstellen.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>Datenobjekte  
 Müssen alle Data-Objekte implementieren die <xref:System.Windows.IDataObject> Schnittstelle, die den folgenden Satz von Methoden bereitstellt, mit denen ein, und die Datenübertragung zu erleichtern.  
  
|Methode|Zusammenfassung|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Ruft ein Datenobjekt in einem angegebenen Datenformat ab.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Überprüft, ob die Daten in verfügbar ist, oder eine angegebene Format konvertiert werden können.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Gibt eine Liste der Formate, die die Daten in diesem Datenobjekt befindet sich in oder konvertiert werden können.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Speichert die angegebenen Daten in diesem Datenobjekt.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stellt eine grundlegende Implementierung der <xref:System.Windows.IDataObject> in die <xref:System.Windows.DataObject> Klasse. Die Aktie <xref:System.Windows.DataObject> Klasse ist für viele häufige Datenübertragungsszenarien ausreichend.  
  
 Es gibt mehrere vordefinierte Formate, z. B. Bitmap, CSV, Datei, HTML, RTF, Zeichenfolge, Text und Audio. Informationen zu vordefinierten Datenformaten, die im Lieferumfang [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter den <xref:System.Windows.DataFormats> Referenzthema-Klasse.  
  
 Datenobjekte sind im Allgemeinen eine Funktion für Automatisches Umwandeln von Daten, die beim Extrahieren von Daten in einem Format in ein anderes Format: Diese Funktion wird als automatische Konvertierung bezeichnet. Bei der Abfrage der Datenformate in einem Datenobjekt verfügbar können Datenformate, die automatisch von systemeigene Datenformate gefiltert werden, durch den Aufruf der <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> oder <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> -Methode und Angeben der `autoConvert` Parameter als `false`.  Hinzufügen von Daten an ein Datenobjekt mit der <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> Methode, die automatische Konvertierung von Daten kann durch Festlegen von verboten werden die `autoConvert` Parameter `false`.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>Arbeiten mit Datenobjekten  
 Dieser Abschnitt beschreibt allgemeine Verfahren zum Erstellen von und Arbeiten mit Datenobjekten.  
  
### <a name="creating-new-data-objects"></a>Erstellen von neuen Datenobjekten  
 Die <xref:System.Windows.DataObject> Klasse bietet mehrere überladene Konstruktoren, die ermöglichen, eine neue Auffüllen <xref:System.Windows.DataObject> Instanz mit einem einzelnen Data-Daten-Paar-Format.  
  
 Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen Konstruktoren <xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) zum Initialisieren des Daten-Objekts mit einer Zeichenfolge und einem angegebenen Datenformat.  In diesem Fall wird das Format der Daten durch eine Zeichenfolge angegeben. die <xref:System.Windows.DataFormats> Klasse bietet eine Reihe von vordefinierten Typzeichenfolgen. Automatische Konvertierung von der gespeicherten Daten ist standardmäßig zulässig.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Weitere Beispiele für Code, der ein Objekt erstellt wird, finden Sie unter [Erstellen eines Datenobjekts](how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Das Speichern von Daten in mehreren Formaten  
 Ein einzelnes Datenobjekt kann zum Speichern von Daten in mehreren Formaten zur Verfügung.   Strategische Nutzung von mehreren Datenformaten in einem einzelnen Datenobjekt wird möglicherweise das Datenobjekt, das von einer größeren Vielzahl von Dropzielen als genutzt werden, wenn nur ein einziges Datenformat dargestellt werden kann.  Beachten Sie, dass im Allgemeinen muss eine Ziehquelle unabhängig von der die Datenformate von möglichen Ablageziele genutzt werden.  
  
 Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> Methode zum Hinzufügen von Daten an ein Datenobjekt in mehreren Formaten.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Abfragen von einem Datenobjekt für die verfügbaren Formate  
 Da ein einzelnes Datenobjekt eine beliebige Anzahl von Datenformate enthalten kann, enthalten die Datenobjekte Funktionen zum Abrufen einer Liste der verfügbaren Datenformate.  
  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> -Überladung verwenden, um ein Array von Zeichenfolgen, die alle verfügbaren Datenformate in einem Datenobjekt (systemeigene und durch automatische Konvertierung) abrufen.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Weitere Beispiele für Code, ein Datenobjekt auf verfügbaren Datenformaten abgefragt, wird, finden Sie unter [Auflisten der Datenformate in einem Datenobjekt](how-to-list-the-data-formats-in-a-data-object.md).  Beispiele für Abfragen ein Datenobjekt auf das Vorhandensein von einem bestimmten Datenformat, finden Sie unter [zu bestimmen, ob ein Datenformat vorhanden ist. in einem Datenobjekt](how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### <a name="retrieving-data-from-a-data-object"></a>Abrufen von Daten von einem Datenobjekt  
 Abrufen von Daten von einem Datenobjekt in einem bestimmten Format umfasst einen Aufruf der einfach die <xref:System.Windows.DataObject.GetData%2A> Methoden und das gewünschte Datenformat angibt.  Eines der <xref:System.Windows.DataObject.GetDataPresent%2A> Methoden können verwendet werden, um auf das Vorhandensein von einem bestimmten Datenformat zu überprüfen.  <xref:System.Windows.DataObject.GetData%2A> Gibt zurück, die Daten in eine <xref:System.Object>; abhängig von das Datenformat dieses Objekt in einen Container typspezifische umgewandelt werden kann.  
  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> -Überladung verwenden, um zu überprüfen, ob ein angegebenes Datenformat verfügbar ist (systemeigene oder durch automatische Konvertierung). Wenn das angegebene Format verfügbar ist, im Beispiel ruft ab, die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29> Methode.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Weitere Beispiele für Code, der von einem Datenobjekt Daten abruft, finden Sie unter [Abrufen von Daten in einem bestimmten Datenformat](how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Entfernen von Daten von einem Datenobjekt  
 Daten können nicht direkt von einem Datenobjekt entfernt werden.  Um Daten von einem Datenobjekt effektiv zu entfernen, gehen Sie folgendermaßen vor:  
  
1. Erstellen Sie ein neues Objekt, das nur die Daten enthalten, die Sie beibehalten möchten.  
  
2. "Copy" die gewünschten Daten aus dem alten Datenobjekt auf das neue Objekt.  Um die Daten kopieren möchten, verwenden Sie eine der der <xref:System.Windows.DataObject.GetData%2A> Methoden zum Abrufen einer <xref:System.Object> , enthält die unformatierten Daten und verwenden Sie eine der der <xref:System.Windows.DataObject.SetData%2A> Methoden, um die Daten auf das neue Objekt hinzuzufügen.  
  
3. Ersetzen Sie das alte Objekt durch die neue ein.  
  
> [!NOTE]
>  Die <xref:System.Windows.DataObject.SetData%2A> Methoden nur Daten an ein Datenobjekt hinzufügen; sie sind Daten, nicht ersetzen, auch wenn die Daten und das Format der Daten genau einem vorherigen Aufruf identisch sind. Aufrufen von <xref:System.Windows.DataObject.SetData%2A> Format führt für die gleichen Daten und Daten zweimal in das Daten/Datenformat wird zweimal im Datenobjekt vorhanden sind.
