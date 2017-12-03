---
title: 'Gewusst wie: Serialisieren eines Objekts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 92f7d19d84f8146a5c7933119874f4223dc20b6b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="855f5-102">Gewusst wie: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="855f5-102">How to: Serialize an Object</span></span>
<span data-ttu-id="855f5-103">Wenn Sie ein Objekt serialisieren möchten, erstellen Sie zuerst das zu serialisierende Objekt und legen dann dessen öffentliche Eigenschaften und Felder fest.</span><span class="sxs-lookup"><span data-stu-id="855f5-103">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="855f5-104">Dazu müssen Sie das Transportformat angeben, in dem der XML-Stream gespeichert werden soll: als Stream oder als Datei.</span><span class="sxs-lookup"><span data-stu-id="855f5-104">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="855f5-105">Wenn der XML-Stream beispielsweise in einer permanenten Form gespeichert werden muss, erstellen Sie ein <xref:System.IO.FileStream>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="855f5-105">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="855f5-106">Weitere Beispiele zur XML-Serialisierung finden Sie unter [Examples of XML Serialization (Beispiele für die XML-Serialisierung)](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="855f5-106">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="855f5-107">So serialisieren Sie ein Objekt</span><span class="sxs-lookup"><span data-stu-id="855f5-107">To serialize an object</span></span>  
  
1.  <span data-ttu-id="855f5-108">Erstellen Sie das Objekt, und legen Sie seine öffentlichen Felder und Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="855f5-108">Create the object and set its public fields and properties.</span></span>  
  
2.  <span data-ttu-id="855f5-109">Erstellen Sie unter Verwendung des Objekttyps ein <xref:System.Xml.Serialization.XmlSerializer>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="855f5-109">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="855f5-110">Weitere Informationen hierzu finden Sie in den Ausführungen zu den <xref:System.Xml.Serialization.XmlSerializer>-Klassenkonstruktoren.</span><span class="sxs-lookup"><span data-stu-id="855f5-110">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3.  <span data-ttu-id="855f5-111">Rufen Sie die <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>-Methode auf, um einen XML-Stream oder eine Darstellung in Dateiform der öffentlichen Eigenschaften und Felder des Objekts zu generieren.</span><span class="sxs-lookup"><span data-stu-id="855f5-111">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="855f5-112">Im folgenden Beispiel wird eine Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="855f5-112">The following example creates a file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="855f5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="855f5-113">See Also</span></span>  
 [<span data-ttu-id="855f5-114">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="855f5-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="855f5-115">Vorgehensweise: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="855f5-115">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
