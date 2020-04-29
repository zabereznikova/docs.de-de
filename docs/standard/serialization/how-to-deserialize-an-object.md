---
title: 'Gewusst wie: Deserialisieren eines Objekts mithilfe von XMlSerializer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: c24ba466a208fe5abdbf565169c41c4ee3f47482
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559897"
---
# <a name="how-to-deserialize-an-object-using-xmlserializer"></a><span data-ttu-id="5b6a3-102">Gewusst wie: Deserialisieren eines Objekts mithilfe von XMlSerializer</span><span class="sxs-lookup"><span data-stu-id="5b6a3-102">How to deserialize an object using XmlSerializer</span></span>

<span data-ttu-id="5b6a3-103">Beim Deserialisieren eines Objekts wird durch das Transportformat festgelegt, ob ein Stream- oder ein Dateiobjekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-103">When you deserialize an object, the transport format determines whether you will create a stream or file object.</span></span> <span data-ttu-id="5b6a3-104">Nachdem das Transportformat festgelegt wurde, können Sie je nach Bedarf die <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>-Methode oder <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-104">After the transport format is determined, you can call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> or <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> methods, as required.</span></span>

## <a name="to-deserialize-an-object"></a><span data-ttu-id="5b6a3-105">So deserialisieren Sie ein Objekt</span><span class="sxs-lookup"><span data-stu-id="5b6a3-105">To deserialize an object</span></span>

1. <span data-ttu-id="5b6a3-106">Erstellen Sie ein <xref:System.Xml.Serialization.XmlSerializer>-Objekt unter Verwendung des zu deserialisierenden Objekttyps.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-106">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object to deserialize.</span></span>

1. <span data-ttu-id="5b6a3-107">Rufen Sie die <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>-Methode auf, um ein Replikat des Objekts zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="5b6a3-107">Call the <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> method to produce a replica of the object.</span></span> <span data-ttu-id="5b6a3-108">Beim Deserialisieren müssen Sie das zurückgegebene Objekt in den ursprünglichen Objekttyp umwandeln. Dies wird im folgenden Beispiel gezeigt, in dem das Objekt aus einer Datei deserialisiert wird (es könnte aber auch aus einem Stream deserialsiert werden).</span><span class="sxs-lookup"><span data-stu-id="5b6a3-108">When deserializing, you must cast the returned object to the type of the original, as shown in the following example, which deserializes the object from a file (although it could also be deserialized from a stream).</span></span>

    ```vb
    ' Construct an instance of the XmlSerializer with the type
    ' of object that is being deserialized.
    Dim mySerializer As New XmlSerializer(GetType(MySerializableClass))
    ' To read the file, create a FileStream.
    Dim myFileStream As New FileStream("myFileName.xml", FileMode.Open)
    ' Call the Deserialize method and cast to the object type.
    Dim myObject = CType( _
    mySerializer.Deserialize(myFileStream), MySerializableClass)
    ```

    ```csharp
    // Construct an instance of the XmlSerializer with the type
    // of object that is being deserialized.
    var mySerializer = new XmlSerializer(typeof(MySerializableClass));
    // To read the file, create a FileStream.
    var myFileStream = new FileStream("myFileName.xml", FileMode.Open);
    // Call the Deserialize method and cast to the object type.
    var myObject = (MySerializableClass) mySerializer.Deserialize(myFileStream)
    ```

## <a name="see-also"></a><span data-ttu-id="5b6a3-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b6a3-109">See also</span></span>

- [<span data-ttu-id="5b6a3-110">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="5b6a3-110">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- <span data-ttu-id="5b6a3-111">[How to: Serialisieren eines Objekts](how-to-serialize-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="5b6a3-111">[How to: Serialize an Object](how-to-serialize-an-object.md)</span></span>
