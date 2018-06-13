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
ms.openlocfilehash: ff596dc7428c9d105a27999f216d33e735e35a22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540318"
---
# <a name="data-and-data-objects"></a>Daten und Datenobjekte
Daten, die als Teil eines Drag-and-Drop-Vorgangs übertragen werden, werden in einem Datenobjekt gespeichert.  Im Prinzip besteht aus einem Datenobjekt eine oder mehrere der folgenden Paare:  
  
-   Eine <xref:System.Object> , die die tatsächlichen Daten enthält.  
  
-   Eine entsprechende Daten Format-ID.  
  
 Die Daten selbst können bestehen aus Elementen, die als Basis dargestellt werden kann <xref:System.Object>.  Das entsprechende Datenformat ist eine Zeichenfolge oder <xref:System.Type> , ein Hinweis darüber, was das Datenformat ist bereitstellt.  Datenobjekte unterstützen hosting mehrere Paare von Data-Daten-Format. Dadurch wird ein einzelnes Datenobjekt Daten in verschiedenen Formaten bereitstellen.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>Datenobjekte  
 Alle Datenobjekte müssen implementieren die <xref:System.Windows.IDataObject> -Schnittstelle, die den folgenden Standardsatz von Methoden bereitstellt, mit denen und vereinfachen die Übertragung von Daten.  
  
|Methode|Zusammenfassung|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Ruft ein Datenobjekt in einem Format angegebenen Daten ab.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Überprüft, ob die Daten in verfügbar ist, oder in einem angegebenen Format konvertiert werden können.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Gibt eine Liste der Formate, die die Daten in diesem Datenobjekt konvertiert werden können oder gespeichert ist.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Speichert die angegebenen Daten in diesem Datenobjekt.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Stellt eine grundlegende Implementierung der <xref:System.Windows.IDataObject> in die <xref:System.Windows.DataObject> Klasse. Der Bestand <xref:System.Windows.DataObject> Klasse ist für viele häufige Szenarien für die Data-Übertragung ausreichend.  
  
 Es gibt mehrere vordefinierte Formate, z. B. mithilfe einer Bitmap, CSV-Datei, HTML, RTF, Zeichenfolge, Text und Audio. Informationen zum Lieferumfang vordefinierter Datenformate [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], finden Sie unter der <xref:System.Windows.DataFormats> Referenzthema-Klasse.  
  
 Datenobjekte enthalten häufig eine Funktion für automatischen Konvertierung, die beim Extrahieren von Daten in einem Format in ein anderes Format gespeicherte Daten; Diese Funktion wird als automatische Konvertierung bezeichnet. Beim Abfragen der in einem Datenobjekt verfügbaren Datenformate können Datenformate, die automatisch von systemeigene Datenformate gefiltert werden, durch Aufrufen der <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> oder <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> -Methode und Angeben der `autoConvert` Parameter als `false`.  Hinzufügen von Daten an ein Datenobjekt mit der <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> Methode, die automatische Konvertierung von Daten kann untersagt werden, durch Festlegen der `autoConvert` Parameter `false`.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>Arbeiten mit Data-Objekte  
 Dieser Abschnitt beschreibt allgemeine Techniken zum Erstellen und Arbeiten mit Data-Objekten.  
  
### <a name="creating-new-data-objects"></a>Erstellen neuer Datenobjekte  
 Die <xref:System.Windows.DataObject> -Klasse stellt mehrere überladene Konstruktoren, die das Auffüllen einer neuen erleichtern <xref:System.Windows.DataObject> Instanz mit einem einzelnen Data-Daten-Paar Format.  
  
 Im folgenden Codebeispiel wird ein neues Datenobjekt erstellt und verwendet einen der überladenen Konstruktoren <xref:System.Windows.DataObject.%23ctor%2A>(<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>) zum Initialisieren des Objekts Daten mit einer Zeichenfolge und einem angegebenen Format.  In diesem Fall wird das Datenformat durch eine Zeichenfolge angegeben. die <xref:System.Windows.DataFormats> Klasse bietet eine Reihe von vordefinierten Typzeichenfolgen. Automatische Konvertierung der gespeicherten Daten ist standardmäßig zulässig.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Weitere Beispiele für Code, der ein Datenobjekt erstellt wird, finden Sie unter [Erstellen eines Datenobjekts](../../../../docs/framework/wpf/advanced/how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Das Speichern von Daten in mehreren Formaten  
 Ein einzelnes Datenobjekt kann Daten in verschiedenen Formaten zu speichern.   Strategische Verwendung des mehrere Datenformate innerhalb eines einzelnen Objekts wird möglicherweise das Datenobjekt kann durch eine größere Bandbreite von Ablagezielen als wenn nur ein einziges Datenformat dargestellt werden konnte.  Beachten Sie, dass im Allgemeinen eine Quelle des Ziehvorgangs über die Datenformate agnostisch sein muss, die möglichen Ablageziele Ereignisformat sind.  
  
 Das folgende Beispiel zeigt, wie Sie die <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> Methode zum Hinzufügen von Daten an ein Datenobjekt in verschiedenen Formaten.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Abfragen eines Datenobjekts für die verfügbaren Formate  
 Da ein einzelnes Datenobjekt eine beliebige Anzahl von Datenformate enthalten kann, enthalten Datenobjekte Funktionen zum Abrufen einer Liste der verfügbaren Datenformate.  
  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> methodenüberladung, um ein Array von Zeichenfolgen, die alle verfügbaren Datenformate in ein Datenobjekt (sowohl systemeigene als auch durch automatische Konvertierung) abrufen.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Weitere Beispiele für Code, der ein Datenobjekt nach verfügbaren Datenformaten abgefragt wird, finden Sie unter [Auflisten der Datenformate in einem Datenobjekt](../../../../docs/framework/wpf/advanced/how-to-list-the-data-formats-in-a-data-object.md).  Beispiele für Abfragen eines Datenobjekts für das Vorhandensein eines bestimmten Datenformats, finden Sie unter [zu bestimmen, ob ein Datenformat vorhanden ist in einem Datenobjekt](../../../../docs/framework/wpf/advanced/how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### <a name="retrieving-data-from-a-data-object"></a>Abrufen von Daten aus einem Datenobjekt  
 Abrufen von Daten aus einem Datenobjekt in einem bestimmten Format einfach beinhaltet den Aufruf eines der <xref:System.Windows.DataObject.GetData%2A> Methoden und die gewünschten Daten-Format angibt.  Eines der <xref:System.Windows.DataObject.GetDataPresent%2A> Methoden können verwendet werden, um das Vorhandensein eines bestimmten Formats zu überprüfen.  <xref:System.Windows.DataObject.GetData%2A> Gibt die Daten in eine <xref:System.Object>; je nach das Datenformat dieses Objekts zu einem Container typspezifische umgewandelt werden kann.  
  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> Überladung zum Überprüfen, ob ein angegebenes Datenformat verfügbar ist (systemeigen oder durch automatische Konvertierung). Wenn das angegebene Format verfügbar ist, ruft das Beispiel die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29> Methode.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Weitere Beispiele für Code, der Daten aus einem Datenobjekt abgerufen werden, finden Sie unter [Abrufen von Daten in ein bestimmtes Datenformat](../../../../docs/framework/wpf/advanced/how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Entfernen von Daten aus einem Datenobjekt  
 Daten können nicht direkt von einem Datenobjekt entfernt werden.  Um Daten von einem Datenobjekt effektiv zu entfernen, gehen Sie folgendermaßen vor:  
  
1.  Erstellen Sie ein neues Datenobjekt, das nur die Daten enthalten, die Sie beibehalten möchten.  
  
2.  "Kopieren" die gewünschten Daten aus dem alten Datenobjekt an das neue Objekt.  Um die Daten kopieren möchten, verwenden Sie eine der der <xref:System.Windows.DataObject.GetData%2A> Methoden zum Abrufen einer <xref:System.Object> , enthält die Rohdaten, und verwenden Sie eine der der <xref:System.Windows.DataObject.SetData%2A> Methoden zum Hinzufügen von Daten auf das neue Datenobjekt.  
  
3.  Ersetzen Sie das alte Datenobjekt durch das neue Element.  
  
> [!NOTE]
>  Die <xref:System.Windows.DataObject.SetData%2A> Methoden nur Daten an ein Datenobjekt hinzufügen; sie Daten nicht ersetzen, selbst wenn die Daten und das Datenformat genau mit einem vorherigen Aufruf identisch sind. Aufrufen von <xref:System.Windows.DataObject.SetData%2A> Format führt für die gleichen Daten und die Daten zweimal im Format Data-Daten, die in das Datenobjekt doppelt vorhanden.
