---
title: Konvertierung von XML-Datentypen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2f5f5d27b3d21ff12f5eea7613e80e73c5b6597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="e497a-102">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="e497a-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="e497a-103">Der Großteil der Methoden gefunden, eine **XmlConvert** Klasse werden verwendet, um Daten zwischen Zeichenfolgen und stark typisierten Formaten konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e497a-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly-typed formats.</span></span> <span data-ttu-id="e497a-104">Die Methoden sind unabhängig vom Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="e497a-104">Methods are locale independent.</span></span> <span data-ttu-id="e497a-105">Dies bedeutet, dass im Rahmen von Konvertierungen keine Gebietsschemaeinstellungen berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="e497a-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="e497a-106">Lesen von Zeichenfolgen als Typen</span><span class="sxs-lookup"><span data-stu-id="e497a-106">Reading String as types</span></span>  
 <span data-ttu-id="e497a-107">Im folgenden Beispiel liest eine Zeichenfolge und konvertiert sie in einem **"DateTime"** Typ.</span><span class="sxs-lookup"><span data-stu-id="e497a-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="e497a-108">Die folgenden XML-Eingaben sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="e497a-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="e497a-109">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="e497a-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="e497a-110">Dieser Code konvertiert die Zeichenfolge, die die **"DateTime"** Format:</span><span class="sxs-lookup"><span data-stu-id="e497a-110">This code converts the string to the **DateTime** format:</span></span>  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="e497a-111">Schreiben von Zeichenfolgen als Typen</span><span class="sxs-lookup"><span data-stu-id="e497a-111">Writing Strings as types</span></span>  
 <span data-ttu-id="e497a-112">Das folgende Beispiel liest eine **Int32** und in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e497a-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="e497a-113">Die folgenden XML-Eingaben sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="e497a-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="e497a-114">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="e497a-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="e497a-115">Dieser Code konvertiert das **Int32** in einem **Zeichenfolge**:</span><span class="sxs-lookup"><span data-stu-id="e497a-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="e497a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e497a-116">See Also</span></span>  
 [<span data-ttu-id="e497a-117">Konvertieren von Zeichenfolgen in .NET Framework-Datentypen</span><span class="sxs-lookup"><span data-stu-id="e497a-117">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [<span data-ttu-id="e497a-118">Konvertieren von .NET Framework-Typen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e497a-118">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
