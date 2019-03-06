---
title: 'Vorgehensweise: Erstellen eines Datenobjekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
ms.openlocfilehash: f7bdfbf3dba0c700513348195c1d031d4c2c8b65
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370591"
---
# <a name="how-to-create-a-data-object"></a>Vorgehensweise: Erstellen eines Datenobjekts
Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen eines Datenobjekts, das mit den Konstruktoren, die von bereitgestellte der <xref:System.Windows.DataObject> Klasse.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) zum Initialisieren des Daten-Objekts mit einer Zeichenfolge.  In diesem Fall wird ein geeignetes Datenformat automatisch anhand der Typ der gespeicherten Daten bestimmt, und der gespeicherten Daten der automatischen Umstellung ist standardmäßig zulässig.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode ist eine verkürzte Version der oben aufgeführten Code.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) zum Initialisieren des Daten-Objekts mit einer Zeichenfolge und einem angegebenen Datenformat.  In diesem Fall wird das Format der Daten durch eine Zeichenfolge angegeben. die <xref:System.Windows.DataFormats> Klasse bietet eine Reihe von vordefinierten Typzeichenfolgen. Automatische Konvertieren der gespeicherten Daten ist standardmäßig zulässig.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode ist eine verkürzte Version der oben aufgeführten Code.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%2A>) zum Initialisieren des Daten-Objekts mit einer Zeichenfolge und einem angegebenen Datenformat.  In diesem Fall wird das Format der Daten angegeben, indem eine <xref:System.Type> Parameter.  Automatische Konvertieren der gespeicherten Daten ist standardmäßig zulässig.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode ist eine verkürzte Version der oben aufgeführten Code.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode erstellt ein neues Datenobjekt und verwendet einen der überladenen Konstruktoren (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) zum Initialisieren des Daten-Objekts mit einer Zeichenfolge und einem angegebenen Datenformat.  In diesem Fall wird das Format der Daten durch eine Zeichenfolge angegeben. die <xref:System.Windows.DataFormats> Klasse bietet eine Reihe von vordefinierten Typzeichenfolgen. Diese bestimmte Konstruktorüberladung ermöglicht dem Aufrufer angeben, ob die automatische Konvertierung zulässig ist.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a>Beschreibung  
 Der folgende Beispielcode ist eine verkürzte Version der oben aufgeführten Code.  
  
### <a name="code"></a>Code  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.IDataObject>
