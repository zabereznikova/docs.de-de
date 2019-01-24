---
title: 'Vorgehensweise: Deserialisieren eines Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: d0b953e4f570f349edeb80fc2316530494905ec0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583310"
---
# <a name="how-to-deserialize-an-object"></a><span data-ttu-id="2f1ed-102">Vorgehensweise: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="2f1ed-102">How to: Deserialize an Object</span></span>
<span data-ttu-id="2f1ed-103">Beim Deserialisieren eines Objekts wird durch das Transportformat festgelegt, ob ein Stream- oder ein Dateiobjekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2f1ed-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="2f1ed-104">Nachdem das Transportformat festgelegt wurde, können Sie je nach Bedarf die <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>-Methode oder <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2f1ed-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>  
  
### <a name="to-deserialize-an-object"></a><span data-ttu-id="2f1ed-105">So deserialisieren Sie ein Objekt</span><span class="sxs-lookup"><span data-stu-id="2f1ed-105">To deserialize an object</span></span>  
  
1.  <span data-ttu-id="2f1ed-106">Erstellen Sie ein <xref:System.Xml.Serialization.XmlSerializer>-Objekt unter Verwendung des zu deserialisierenden Objekttyps.</span><span class="sxs-lookup"><span data-stu-id="2f1ed-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>  
  
2.  <span data-ttu-id="2f1ed-107">Rufen Sie die <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>-Methode auf, um ein Replikat des Objekts zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="2f1ed-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="2f1ed-108">Beim Deserialisieren müssen Sie das zurückgegebene Objekt in den ursprünglichen Objekttyp umwandeln. Dies wird im folgenden Beispiel gezeigt, in dem das Objekt in eine Datei deserialisiert wird (es könnte aber auch in einen Stream deserialsiert werden).</span><span class="sxs-lookup"><span data-stu-id="2f1ed-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object into a file (although it could also be deserialized into a stream).</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2f1ed-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f1ed-109">See also</span></span>

- [<span data-ttu-id="2f1ed-110">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="2f1ed-110">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="2f1ed-111">Vorgehensweise: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="2f1ed-111">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)
