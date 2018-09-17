---
title: 'Gewusst wie: Serialisieren eines Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
ms.openlocfilehash: e4d6e3edb15dbf5ba4b7ec7f8658fec1a618d315
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45748574"
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="3e247-102">Gewusst wie: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="3e247-102">How to: Serialize an Object</span></span>
<span data-ttu-id="3e247-103">Wenn Sie ein Objekt serialisieren möchten, erstellen Sie zuerst das zu serialisierende Objekt und legen dann dessen öffentliche Eigenschaften und Felder fest.</span><span class="sxs-lookup"><span data-stu-id="3e247-103">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="3e247-104">Dazu müssen Sie das Transportformat angeben, in dem der XML-Stream gespeichert werden soll: als Stream oder als Datei.</span><span class="sxs-lookup"><span data-stu-id="3e247-104">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="3e247-105">Wenn der XML-Stream beispielsweise in einer permanenten Form gespeichert werden muss, erstellen Sie ein <xref:System.IO.FileStream>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="3e247-105">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e247-106">Weitere Beispiele zur XML-Serialisierung finden Sie unter [Examples of XML Serialization (Beispiele für die XML-Serialisierung)](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="3e247-106">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="3e247-107">So serialisieren Sie ein Objekt</span><span class="sxs-lookup"><span data-stu-id="3e247-107">To serialize an object</span></span>  
  
1.  <span data-ttu-id="3e247-108">Erstellen Sie das Objekt, und legen Sie seine öffentlichen Felder und Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="3e247-108">Create the object and set its public fields and properties.</span></span>  
  
2.  <span data-ttu-id="3e247-109">Erstellen Sie unter Verwendung des Objekttyps ein <xref:System.Xml.Serialization.XmlSerializer>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="3e247-109">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="3e247-110">Weitere Informationen hierzu finden Sie in den Ausführungen zu den <xref:System.Xml.Serialization.XmlSerializer>-Klassenkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="3e247-110">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3.  <span data-ttu-id="3e247-111">Rufen Sie die <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>-Methode auf, um einen XML-Stream oder eine Darstellung in Dateiform der öffentlichen Eigenschaften und Felder des Objekts zu generieren.</span><span class="sxs-lookup"><span data-stu-id="3e247-111">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="3e247-112">Im folgenden Beispiel wird eine Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="3e247-112">The following example creates a file.</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new   
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3e247-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e247-113">See also</span></span>

- [<span data-ttu-id="3e247-114">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="3e247-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
- [<span data-ttu-id="3e247-115">Vorgehensweise: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="3e247-115">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
