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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d18b69c2d5baeac77cbdf45bebd6f0c9d5c94d9f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="9c68c-102">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="9c68c-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="9c68c-103">Mit den meisten Methoden in einer **XmlConvert**-Klasse werden Daten zwischen Zeichenfolgen und stark typisierten Formaten konvertiert.</span><span class="sxs-lookup"><span data-stu-id="9c68c-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly-typed formats.</span></span> <span data-ttu-id="9c68c-104">Die Methoden sind unabhängig vom Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="9c68c-104">Methods are locale independent.</span></span> <span data-ttu-id="9c68c-105">Dies bedeutet, dass im Rahmen von Konvertierungen keine Gebietsschemaeinstellungen berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="9c68c-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="9c68c-106">Lesen von Zeichenfolgen als Typen</span><span class="sxs-lookup"><span data-stu-id="9c68c-106">Reading String as types</span></span>  
 <span data-ttu-id="9c68c-107">Im folgenden Beispiel wird eine Zeichenfolge gelesen und in einen **DateTime**-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="9c68c-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="9c68c-108">Die folgenden XML-Eingaben sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="9c68c-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="9c68c-109">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="9c68c-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="9c68c-110">Mit diesem Code wird die Zeichenfolge in das **DateTime**-Format konvertiert:</span><span class="sxs-lookup"><span data-stu-id="9c68c-110">This code converts the string to the **DateTime** format:</span></span>  
  
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
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="9c68c-111">Schreiben von Zeichenfolgen als Typen</span><span class="sxs-lookup"><span data-stu-id="9c68c-111">Writing Strings as types</span></span>  
 <span data-ttu-id="9c68c-112">Im folgenden Beispiel wird ein **Int32**-Typ gelesen und in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="9c68c-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="9c68c-113">Die folgenden XML-Eingaben sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="9c68c-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="9c68c-114">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="9c68c-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="9c68c-115">Mit diesem Code wird der **Int32**-Typ in einen **String** konvertiert:</span><span class="sxs-lookup"><span data-stu-id="9c68c-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c68c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c68c-116">See Also</span></span>  
 [<span data-ttu-id="9c68c-117">Konvertieren von Zeichenfolgen in .NET Framework-Datentypen</span><span class="sxs-lookup"><span data-stu-id="9c68c-117">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [<span data-ttu-id="9c68c-118">Konvertieren von .NET Framework-Typen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9c68c-118">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
