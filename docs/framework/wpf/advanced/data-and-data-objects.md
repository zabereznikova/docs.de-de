---
title: "Daten und Datenobjekte | Microsoft Docs"
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
  - "Datenübertragung [WPF], Drag &amp; Drop"
  - "DataFormats-Klasse [WPF]"
  - "DataObject-Klasse [WPF]"
ms.assetid: 5967d557-1867-420f-a524-ae3af78402da
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Daten und Datenobjekte
Daten, die als Teil eines Drag & Drop\-Vorgangs übertragen werden, werden in einem Datenobjekt gespeichert.  Im Prinzip besteht ein Datenobjekt aus einem oder mehreren der folgenden Paare:  
  
-   Einem <xref:System.Object>, das die eigentlichen Daten enthält  
  
-   Einem entsprechenden Datenformatbezeichner  
  
 Die Daten selbst können aus allem bestehen, was als Basis\-<xref:System.Object> dargestellt werden kann.  Das entsprechende Datenformat ist eine Zeichenfolge oder ein <xref:System.Type>\-Element, das einen Hinweis auf das Format der Daten gibt.  Datenobjekte unterstützen das Hosten mehrerer Daten\-\/Datenformatpaare, sodass ein einzelnes Datenobjekt Daten in mehreren Formaten bereitstellen kann.  
  
<a name="Data_and_Data_Objects"></a>   
## Datenobjekte  
 Alle Datenobjekte müssen die <xref:System.Windows.IDataObject>\-Schnittstelle implementieren, die den folgenden Standardsatz von Methoden bereitstellt, mit denen sich die Datenübertragung durchführen und vereinfachen lässt.  
  
|Methode|Zusammenfassung|  
|-------------|---------------------|  
|<xref:System.Windows.IDataObject.GetData%2A>|Ruft ein Datenobjekt in einem bestimmten Datenformat ab.|  
|<xref:System.Windows.IDataObject.GetDataPresent%2A>|Überprüft, ob die Daten in einem bestimmten Format verfügbar sind oder in dieses Format konvertiert werden können.|  
|<xref:System.Windows.IDataObject.GetFormats%2A>|Gibt eine Liste von Formaten zurück, in denen die Daten in diesem Datenobjekt gespeichert sind bzw. in die diese konvertiert werden können.|  
|<xref:System.Windows.IDataObject.SetData%2A>|Speichert die angegebenen Daten in diesem Datenobjekt.|  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine grundlegende Implementierung von <xref:System.Windows.IDataObject> in der <xref:System.Windows.DataObject>\-Klasse bereit.  Die vordefinierte <xref:System.Windows.DataObject>\-Klasse ist für viele häufige Datenübertragungsszenarien ausreichend.  
  
 Es ist eine Reihe vordefinierter Formate verfügbar, z. B. Bitmap, CSV, Datei, HTML, RTF, Zeichenfolge, Text und Audio.  Informationen zu den vordefinierten Datenformate in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie im Referenzthema zur <xref:System.Windows.DataFormats>\-Klasse.  
  
 Datenobjekte enthalten häufig eine Funktion, um bei der Datenextraktion Daten automatisch aus einem Format in ein anderes Format zu konvertieren. Diese Funktion wird als automatische Konvertierung bezeichnet.  Beim Abfragen der in einem Datenobjekt verfügbaren Datenformate können automatisch konvertierbare Datenformate aus systemeigenen Datenformaten herausgefiltert werden, indem die <xref:System.Windows.DataObject.GetFormats%28System.Boolean%29>\- oder <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29>\-Methode aufgerufen und der `autoConvert`\-Parameter auf `false` festgelegt wird.  Wenn einem Datenobjekt mit der <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%2CSystem.Boolean%29>\-Methode Daten hinzugefügt werden, kann die automatische Konvertierung von Daten durch Festlegen des `autoConvert`\-Parameters auf `false` verhindert werden.  
  
<a name="Working_with_Data_Objects"></a>   
## Arbeiten mit Datenobjekten  
 In diesem Abschnitt werden allgemeine Techniken für das Erstellen von und Arbeiten mit Datenobjekten beschrieben.  
  
### Erstellen neuer Datenobjekte  
 Die <xref:System.Windows.DataObject>\-Klasse stellt mehrere überladene Konstruktoren bereit, die das Auffüllen einer neuen <xref:System.Windows.DataObject>\-Instanz mit einem einzelnen Daten\-\/Datenformatpaar erleichtern.  
  
 Im folgenden Beispielcode wird ein neues Datenobjekt erstellt. Außerdem wird mithilfe von einem der überladenen Konstruktoren <xref:System.Windows.DataObject.%23ctor%2A>\(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>\) das Datenobjekt mit einer Zeichenfolge und einem angegebenen Datenformat initialisiert.  In diesem Fall wird das Datenformat durch eine Zeichenfolge angegeben. Die <xref:System.Windows.DataFormats>\-Klasse stellt einen Satz vordefinierter Typzeichenfolgen bereit.  Die automatische Konvertierung der gespeicherten Daten wird standardmäßig zugelassen.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
 Weitere Beispiele für Code, mit dem ein Datenobjekt erstellt wird, finden Sie unter [Erstellen eines Datenobjekts](../../../../docs/framework/wpf/advanced/how-to-create-a-data-object.md).  
  
### Speichern von Daten in mehreren Formaten  
 Ein einzelnes Datenobjekt kann Daten in mehreren Formaten speichern.  Durch den strategischen Einsatz von mehreren Datenformaten innerhalb eines einzelnen Datenobjekts ist das Datenobjekt möglicherweise für eine größere Zahl von Ablagezielen geeignet, als wenn nur ein einzelnes Datenformat dargestellt werden könnte.  Beachten Sie, dass eine Ziehquelle im Allgemeinen von den Datenformaten, die für mögliche Ablageziele geeignet sind, unabhängig sein muss.  
  
 Im folgenden Beispiel wird gezeigt, wie einem Datenobjekt mithilfe der <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29>\-Methode Daten in mehreren Formaten hinzugefügt werden.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
### Abfragen eines Datenobjekts nach verfügbaren Formaten  
 Da ein einzelnes Datenobjekt beliebig viele Datenformate enthalten kann, enthalten Datenobjekte Funktionen zum Abrufen einer Liste von verfügbaren Datenformaten.  
  
 Im folgenden Beispielcode wird mit der <xref:System.Windows.DataObject.GetFormats%2A>\-Überladung ein Zeichenfolgenarray abgerufen, das alle in einem Datenobjekt verfügbaren Datenformate \(systemeigene und automatisch konvertierbare\) angibt.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
 Weitere Beispiele für Code, mit dem ein Datenobjekt nach verfügbaren Datenformaten abgefragt wird, finden Sie unter [Auflisten der Datenformate in einem Datenobjekt](../../../../docs/framework/wpf/advanced/how-to-list-the-data-formats-in-a-data-object.md).  Beispiele für die Abfrage eines Datenobjekts nach einem bestimmten vorhandenen Datenformat finden Sie unter [Feststellen, ob ein Datenformat in einem Datenobjekt vorhanden ist](../../../../docs/framework/wpf/advanced/how-to-determine-if-a-data-format-is-present-in-a-data-object.md).  
  
### Abrufen von Daten aus einem Datenobjekt  
 Wenn Daten aus einem Datenobjekt in einem bestimmten Format abgerufen werden, wird einfach eine der <xref:System.Windows.DataObject.GetData%2A>\-Methoden unter Angabe des gewünschten Datenformats aufgerufen.  Mit einer der <xref:System.Windows.DataObject.GetDataPresent%2A>\-Methoden kann überprüft werden, ob ein bestimmtes Datenformat vorhanden ist.  <xref:System.Windows.DataObject.GetData%2A> gibt die Daten in einem <xref:System.Object> zurück. Je nach Datenformat kann dieses Objekt in einen typspezifischen Container umgewandelt werden.  
  
 Im folgenden Beispielcode wird mit der <xref:System.Windows.DataObject.GetDataPresent%28System.String%29>\-Überladung überprüft, ob ein angegebenes Datenformat verfügbar ist \(im System oder durch automatische Konvertierung\).  Wenn das angegebene Format verfügbar ist, werden im Beispiel die Daten mit der <xref:System.Windows.DataObject.GetData%28System.String%29>\-Methode abgerufen.  
  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
 Weitere Beispiele für Code, mit dem Daten aus einem Datenobjekt abgerufen werden, finden Sie unter [Abrufen von Daten in einem bestimmten Datenformat](../../../../docs/framework/wpf/advanced/how-to-retrieve-data-in-a-particular-data-format.md).  
  
### Entfernen von Daten aus einem Datenobjekt  
 Daten können aus einem Datenobjekt nicht direkt entfernt werden.  Um Daten aus einem Datenobjekt wirksam zu entfernen, gehen Sie folgendermaßen vor:  
  
1.  Erstellen Sie ein neues Datenobjekt, das nur die Daten enthält, die Sie beibehalten möchten.  
  
2.  "Kopieren" Sie die gewünschten Daten aus dem alten Datenobjekt in das neue Datenobjekt.  Kopieren Sie die Daten mit einer der <xref:System.Windows.DataObject.GetData%2A>\-Methoden, um ein <xref:System.Object> abzurufen, das die unformatierten Daten enthält. Fügen Sie anschließend mit einer der <xref:System.Windows.DataObject.SetData%2A>\-Methoden dem neuen Datenobjekt die Daten hinzu.  
  
3.  Ersetzen Sie das alte Datenobjekt durch das neue.  
  
> [!NOTE]
>  Mit den <xref:System.Windows.DataObject.SetData%2A>\-Methoden werden einem Datenobjekt nur Daten hinzugefügt. Es werden damit keine Daten ersetzt, selbst wenn die Daten und das Datenformat mit einem vorhergehenden Aufruf vollständig übereinstimmen.  Wenn <xref:System.Windows.DataObject.SetData%2A> zweimal für dieselben Daten und dasselbe Datenformat aufgerufen wird, führt dies dazu, dass die Daten und das Datenformat zweimal im Datenobjekt vorhanden sind.