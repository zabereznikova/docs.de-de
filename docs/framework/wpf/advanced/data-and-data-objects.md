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
ms.openlocfilehash: 532c254f997da183b073ddc9e00b4364ecfcd739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186340"
---
# <a name="data-and-data-objects"></a>Daten und Datenobjekte
Daten, die im Rahmen eines Drag-and-Drop-Vorgangs übertragen werden, werden in einem Datenobjekt gespeichert.  Ein Datenobjekt besteht konzeptionell aus einem oder mehreren der folgenden Paare:  
  
- Eine, <xref:System.Object> die die tatsächlichen Daten enthält.  
  
- Ein entsprechender Datenformatbezeichner.  
  
 Die Daten selbst können aus allem bestehen, <xref:System.Object>was als Basis dargestellt werden kann.  Das entsprechende Datenformat ist <xref:System.Type> eine Zeichenfolge oder gibt einen Hinweis darauf, in welchem Format sich die Daten befindet.  Datenobjekte unterstützen das Hosten mehrerer Daten-/Datenformatpaare; Dadurch kann ein einzelnes Datenobjekt Daten in mehreren Formaten bereitstellen.  
  
<a name="Data_and_Data_Objects"></a>
## <a name="data-objects"></a>Datenobjekte  
 Alle Datenobjekte müssen <xref:System.Windows.IDataObject> die Schnittstelle implementieren, die die folgenden Standardmethoden bereitstellt, die die Datenübertragung ermöglichen und erleichtern.  
  
|Methode|Zusammenfassung|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Ruft ein Datenobjekt in einem bestimmten Datenformat ab.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Überprüft, ob die Daten in einem bestimmten Format verfügbar sind oder in dieses Format konvertiert werden können.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Gibt eine Liste von Formaten zurück, in denen die Daten in diesem Datenobjekt gespeichert sind bzw. in die diese konvertiert werden können.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Speichert die angegebenen Daten in diesem Datenobjekt.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet eine grundlegende <xref:System.Windows.IDataObject> Implementierung <xref:System.Windows.DataObject> von in der Klasse. Die <xref:System.Windows.DataObject> Bestandsklasse ist für viele gängige Datenübertragungsszenarien ausreichend.  
  
 Es gibt mehrere vordefinierte Formate, z. B. Bitmap, CSV, Datei, HTML, RTF, Zeichenfolge, Text und Audio. Informationen zu vordefinierten Datenformaten, die mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bereitgestellt werden, finden Sie im <xref:System.Windows.DataFormats> Klassenreferenzthema.  
  
 Datenobjekte enthalten in der Regel eine Möglichkeit, in einem Format gespeicherte Daten beim Extrahieren von Daten automatisch in ein anderes Format zu konvertieren. Diese Funktion wird als Auto-Convert bezeichnet. Bei der Abfrage nach den in einem Datenobjekt verfügbaren Datenformaten können automatisch konvertierbare Datenformate aus systemeigenen Datenformaten gefiltert werden, indem die <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> oder-Methode <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> aufgerufen und der `autoConvert` Parameter als `false`angegeben wird.  Beim Hinzufügen von Daten zu <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> einem Datenobjekt mit der Methode kann `autoConvert` die `false`automatische Konvertierung von Daten durch Festlegen des Parameters auf verboten werden.  
  
<a name="Working_with_Data_Objects"></a>
## <a name="working-with-data-objects"></a>Arbeiten mit Datenobjekten  
 In diesem Abschnitt werden gängige Techniken zum Erstellen und Arbeiten mit Datenobjekten beschrieben.  
  
### <a name="creating-new-data-objects"></a>Erstellen neuer Datenobjekte  
 Die <xref:System.Windows.DataObject> Klasse stellt mehrere überladene Konstruktoren <xref:System.Windows.DataObject> bereit, die das Auffüllen einer neuen Instanz mit einem einzelnen Daten-/Datenformatpaar erleichtern.  
  
 Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet <xref:System.Windows.DataObject.%23ctor%2A><xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>einen der überladenen Konstruktoren ( ), um das Datenobjekt mit einer Zeichenfolge und einem angegebenen Datenformat zu initialisieren.  In diesem Fall wird das Datenformat durch eine Zeichenfolge angegeben. Die <xref:System.Windows.DataFormats> Klasse stellt einen Satz vordefinierter Typzeichenfolgen bereit. Die automatische Konvertierung der gespeicherten Daten ist standardmäßig zulässig.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Weitere Beispiele für Code, der ein Datenobjekt erstellt, finden Sie unter [Erstellen eines Datenobjekts](how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Speichern von Daten in mehreren Formaten  
 Ein einzelnes Datenobjekt kann Daten in mehreren Formaten speichern.   Die strategische Verwendung mehrerer Datenformate innerhalb eines einzelnen Datenobjekts macht das Datenobjekt potenziell durch eine größere Anzahl von Drop-Zielen verbrauchsfähig, als wenn nur ein einzelnes Datenformat dargestellt werden könnte.  Beachten Sie, dass eine Ziehquelle im Allgemeinen agnostisch über die Datenformate sein muss, die durch potenzielle Ablageziele verbrauchsfähig sind.  
  
 Das folgende Beispiel zeigt, <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> wie Sie die Methode verwenden, um Einem Datenobjekt Daten in mehreren Formaten hinzuzufügen.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Abfragen eines Datenobjekts nach verfügbaren Formaten  
 Da ein einzelnes Datenobjekt eine beliebige Anzahl von Datenformaten enthalten kann, enthalten Datenobjekte Funktionen zum Abrufen einer Liste verfügbarer Datenformate.  
  
 Der folgende Beispielcode <xref:System.Windows.DataObject.GetFormats%2A> verwendet die Überladung, um ein Array von Zeichenfolgen abzurufen, die alle in einem Datenobjekt verfügbaren Datenformate angibt (sowohl systemeigene als auch durch automatische Konvertierung).  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Weitere Beispiele für Code, der ein Datenobjekt nach verfügbaren Datenformaten abfragt, finden Sie unter [Auflisten der Datenformate in einem Datenobjekt](how-to-list-the-data-formats-in-a-data-object.md).  Beispiele für das Abfragen eines Datenobjekts nach einem bestimmten Datenformat finden Sie unter [Bestimmen, ob ein Datenformat in einem Datenobjekt vorhanden ist.](how-to-determine-if-a-data-format-is-present-in-a-data-object.md)  
  
### <a name="retrieving-data-from-a-data-object"></a>Abrufen von Daten aus einem Datenobjekt  
 Das Abrufen von Daten aus einem Datenobjekt in <xref:System.Windows.DataObject.GetData%2A> einem bestimmten Format umfasst einfach das Aufrufen einer der Methoden und das Angeben des gewünschten Datenformats.  Eine der <xref:System.Windows.DataObject.GetDataPresent%2A> Methoden kann verwendet werden, um das Vorhandensein eines bestimmten Datenformats zu überprüfen.  <xref:System.Windows.DataObject.GetData%2A>gibt die Daten <xref:System.Object>in einem zurück; Je nach Datenformat kann dieses Objekt in einen typspezifischen Container umgegossen werden.  
  
 Der folgende Beispielcode <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> verwendet die Überladung, um zu überprüfen, ob ein angegebenes Datenformat verfügbar ist (systemativ oder durch automatische Konvertierung). Wenn das angegebene Format verfügbar ist, ruft das <xref:System.Windows.DataObject.GetData%28System.String%29> Beispiel die Daten mithilfe der Methode ab.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Weitere Beispiele für Code, der Daten aus einem Datenobjekt abruft, finden Sie unter Abrufen von [Daten in einem bestimmten Datenformat](how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Entfernen von Daten aus einem Datenobjekt  
 Daten können nicht direkt aus einem Datenobjekt entfernt werden.  Gehen Sie folgendzulande vor, um Daten effektiv aus einem Datenobjekt zu entfernen:  
  
1. Erstellen Sie ein neues Datenobjekt, das nur die Daten enthält, die Sie beibehalten möchten.  
  
2. "Kopieren" Sie die gewünschten Daten aus dem alten Datenobjekt in das neue Datenobjekt.  Um die Daten zu kopieren, verwenden Sie eine der <xref:System.Windows.DataObject.GetData%2A> Methoden zum Abrufen einer, <xref:System.Object> die die Rohdaten enthält, und verwenden Sie dann eine der <xref:System.Windows.DataObject.SetData%2A> Methoden, um die Daten dem neuen Datenobjekt hinzuzufügen.  
  
3. Ersetzen Sie das alte Datenobjekt durch das neue.  
  
> [!NOTE]
> Die <xref:System.Windows.DataObject.SetData%2A> Methoden fügen einem Datenobjekt nur Daten hinzu. Sie ersetzen keine Daten, auch wenn die Daten und das Datenformat genau mit dem eines vorherigen Aufrufs identisch sind. Wenn <xref:System.Windows.DataObject.SetData%2A> Sie zweimal für dasselbe Daten- und Datenformat aufrufen, wird das Daten-/Datenformat zweimal im Datenobjekt angezeigt.
