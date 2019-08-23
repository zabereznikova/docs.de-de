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
ms.openlocfilehash: 4b948a64a14df7ea79b54b810f734056d57ef406
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964866"
---
# <a name="data-and-data-objects"></a>Daten und Datenobjekte
Daten, die als Teil eines Drag & Drop-Vorgangs übertragen werden, werden in einem Datenobjekt gespeichert.  Konzeptionell besteht ein Datenobjekt aus einem oder mehreren der folgenden Paare:  
  
- Ein <xref:System.Object> , das die eigentlichen Daten enthält.  
  
- Ein entsprechender Datenformat Bezeichner.  
  
 Die Daten selbst können aus allen Elementen bestehen, die als Basis <xref:System.Object>dargestellt werden können.  Das entsprechende Datenformat ist eine Zeichenfolge <xref:System.Type> oder ein Hinweis darauf, in welchem Format sich die Daten befinden.  Datenobjekte unterstützen das Hosting mehrerer Daten/Datenformat Paare. Dadurch kann ein einzelnes Datenobjekt Daten in mehreren Formaten bereitstellen.  
  
<a name="Data_and_Data_Objects"></a>   
## <a name="data-objects"></a>Datenobjekte  
 Alle Datenobjekte müssen die <xref:System.Windows.IDataObject> -Schnittstelle implementieren, die den folgenden Standardsatz von Methoden bereitstellt, die die Datenübertragung aktivieren und vereinfachen.  
  
|Methode|Zusammenfassung|  
|------------|-------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Ruft ein Datenobjekt in einem angegebenen Datenformat ab.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Überprüft, ob die Daten in einem angegebenen Format verfügbar sind oder in dieses konvertiert werden können.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Gibt eine Liste von Formaten zurück, in denen die Daten in diesem Datenobjekt gespeichert sind oder in die konvertiert werden kann.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Speichert die angegebenen Daten in diesem Datenobjekt.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt eine grundlegende Implementierung <xref:System.Windows.IDataObject> von in <xref:System.Windows.DataObject> der-Klasse bereit. Die Aktien <xref:System.Windows.DataObject> Klasse reicht für viele gängige Datenübertragungs Szenarien aus.  
  
 Es gibt mehrere vordefinierte Formate, wie z. b. Bitmap, CSV, File, HTML, RTF, String, Text und Audiodaten. Informationen zu vordefinierten Datenformaten, die mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bereitgestellt werden, finden Sie im <xref:System.Windows.DataFormats> Thema zur Klassenreferenz.  
  
 Datenobjekte enthalten im Allgemeinen eine Möglichkeit zum automatischen Umrechnen von Daten, die in einem Format in ein anderes Format gespeichert sind, während Daten extrahiert werden. Diese Funktion wird als Auto-Convert bezeichnet. Beim Abfragen der Datenformate, die in einem Datenobjekt verfügbar sind, können automatisch konvertierbare Datenformate aus nativen Datenformaten gefiltert werden, <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29> indem <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> die-Methode oder `autoConvert` die- `false`Methode aufgerufen und der-Parameter als angegeben wird.  Beim Hinzufügen von Daten zu einem Datenobjekt <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29> mit der-Methode kann die automatische Konvertierung von Daten untersagt werden, `autoConvert` indem der `false`-Parameter auf festgelegt wird.  
  
<a name="Working_with_Data_Objects"></a>   
## <a name="working-with-data-objects"></a>Arbeiten mit Datenobjekten  
 In diesem Abschnitt werden allgemeine Techniken zum Erstellen und arbeiten mit Datenobjekten beschrieben.  
  
### <a name="creating-new-data-objects"></a>Erstellen neuer Datenobjekte  
 Die <xref:System.Windows.DataObject> -Klasse stellt mehrere überladene Konstruktoren bereit, die <xref:System.Windows.DataObject> das Auffüllen einer neuen-Instanz mit einem einzelnen Daten-/Datenformatpaar vereinfachen.  
  
 Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen <xref:System.Windows.DataObject.%23ctor%2A>Konstruktoren<xref:System.Windows.DataObject.%23ctor(System.String,System.Object)>(), um das Datenobjekt mit einer Zeichenfolge und einem angegebenen Datenformat zu initialisieren.  In diesem Fall wird das Datenformat durch eine Zeichenfolge angegeben; die <xref:System.Windows.DataFormats> -Klasse stellt einen Satz vordefinierter typzeichenfolgen bereit. Die automatische Konvertierung der gespeicherten Daten ist standardmäßig zulässig.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Weitere Beispiele für Code, der ein Datenobjekt erstellt, finden Sie unter [Erstellen eines Datenobjekts](how-to-create-a-data-object.md).  
  
### <a name="storing-data-in-multiple-formats"></a>Speichern von Daten in mehreren Formaten  
 Ein einzelnes Datenobjekt ist in der Lage, Daten in mehreren Formaten zu speichern.   Durch die strategische Verwendung mehrerer Datenformate innerhalb eines einzelnen Datenobjekts kann das Datenobjekt möglicherweise durch eine größere Vielfalt von Drop-Zielen genutzt werden, als wenn nur ein einzelnes Datenformat dargestellt werden könnte.  Beachten Sie, dass eine Zieh Quelle im Allgemeinen von den Datenformaten agnostisch sein muss, die von potenziellen Ablage Zielen genutzt werden können.  
  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> -Methode zum Hinzufügen von Daten zu einem Datenobjekt in mehreren Formaten verwendet wird.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### <a name="querying-a-data-object-for-available-formats"></a>Abfragen eines Datenobjekts für verfügbare Formate  
 Da ein einzelnes Datenobjekt eine beliebige Anzahl von Datenformaten enthalten kann, enthalten Datenobjekte Funktionen zum Abrufen einer Liste von verfügbaren Datenformaten.  
  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetFormats%2A> -Überladung, um ein Array von Zeichen folgen zu erhalten, das alle in einem Datenobjekt verfügbaren Datenformate (sowohl System eigen als auch durch automatische Konvertierung) anzeigt.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Weitere Beispiele für Code, in dem ein Datenobjekt nach verfügbaren Datenformaten abgefragt wird, finden Sie unter [Auflisten der Datenformate in einem Datenobjekt](how-to-list-the-data-formats-in-a-data-object.md).  Beispiele für das Abfragen eines Datenobjekts auf das vorhanden sein eines bestimmten Datenformats finden Sie unter [bestimmen, ob ein Datenformat in einem Datenobjekt vorhanden ist](how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### <a name="retrieving-data-from-a-data-object"></a>Abrufen von Daten aus einem Datenobjekt  
 Beim Abrufen von Daten aus einem Datenobjekt in einem bestimmten Format wird lediglich eine der <xref:System.Windows.DataObject.GetData%2A> -Methoden aufgerufen und das gewünschte Datenformat angegeben.  Eine der <xref:System.Windows.DataObject.GetDataPresent%2A> -Methoden kann verwendet werden, um zu überprüfen, ob ein bestimmtes Datenformat vorhanden ist.  <xref:System.Windows.DataObject.GetData%2A>Gibt die Daten in einem <xref:System.Object>-Objekt zurück. je nach Datenformat kann dieses Objekt in einen typspezifischen Container umgewandelt werden.  
  
 Der folgende Beispielcode verwendet die <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> -Überladung, um zu überprüfen, ob ein angegebenes Datenformat verfügbar ist (System eigen oder durch automatische Konvertierung). Wenn das angegebene Format verfügbar ist, ruft das Beispiel die Daten mithilfe der <xref:System.Windows.DataObject.GetData%28System.String%29> -Methode ab.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Weitere Beispiele für Code, der Daten aus einem Datenobjekt abruft, finden Sie unter [Abrufen von Daten in einem bestimmten Daten Format](how-to-retrieve-data-in-a-particular-data-format.md).  
  
### <a name="removing-data-from-a-data-object"></a>Entfernen von Daten aus einem Datenobjekt  
 Daten können nicht direkt aus einem Datenobjekt entfernt werden.  Führen Sie die folgenden Schritte aus, um Daten aus einem Datenobjekt effektiv zu entfernen:  
  
1. Erstellen Sie ein neues Datenobjekt, das nur die Daten enthält, die Sie beibehalten möchten.  
  
2. Kopieren Sie die gewünschten Daten aus dem alten Datenobjekt in das neue Datenobjekt.  Um die Daten zu kopieren, verwenden Sie eine <xref:System.Windows.DataObject.GetData%2A> der-Methoden, <xref:System.Object> um einen abzurufen, der die Rohdaten enthält, und verwenden <xref:System.Windows.DataObject.SetData%2A> Sie dann eine der-Methoden, um die Daten dem neuen Datenobjekt hinzuzufügen.  
  
3. Ersetzen Sie das alte Datenobjekt durch das neue Objekt.  
  
> [!NOTE]
> Die <xref:System.Windows.DataObject.SetData%2A> -Methoden fügen nur Daten zu einem Datenobjekt hinzu. Sie ersetzen keine Daten, selbst wenn die Daten und das Datenformat genau mit einem vorherigen-Befehl identisch sind. Das <xref:System.Windows.DataObject.SetData%2A> doppelte aufrufen für die gleichen Daten und das Datenformat führt dazu, dass das Daten-/Datenformat im Datenobjekt zweimal vorhanden ist.
