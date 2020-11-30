---
title: Konvertierung von XML-Datentypen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
ms.openlocfilehash: 108cfbf1ee8ff3d6fbe088d6dd14d0354750cb0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701496"
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="954a8-102">Konvertierung von XML-Datentypen</span><span class="sxs-lookup"><span data-stu-id="954a8-102">Conversion of XML Data Types</span></span>

<span data-ttu-id="954a8-103">Mit den meisten Methoden in einer **XmlConvert**-Klasse werden Daten zwischen Zeichenfolgen und stark typisierten Formaten konvertiert.</span><span class="sxs-lookup"><span data-stu-id="954a8-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly typed formats.</span></span> <span data-ttu-id="954a8-104">Die Methoden sind unabhängig vom Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="954a8-104">Methods are locale independent.</span></span> <span data-ttu-id="954a8-105">Dies bedeutet, dass im Rahmen von Konvertierungen keine Gebietsschemaeinstellungen berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="954a8-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="954a8-106">Lesen von Zeichenfolgen als Typen</span><span class="sxs-lookup"><span data-stu-id="954a8-106">Reading String as types</span></span>  

 <span data-ttu-id="954a8-107">Im folgenden Beispiel wird eine Zeichenfolge gelesen und in einen **DateTime**-Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="954a8-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="954a8-108">Die folgenden XML-Eingaben sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="954a8-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="954a8-109">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="954a8-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="954a8-110">Mit diesem Code wird die Zeichenfolge in das **DateTime**-Format konvertiert:</span><span class="sxs-lookup"><span data-stu-id="954a8-110">This code converts the string to the **DateTime** format:</span></span>  
  
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
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="954a8-111">Schreiben von Zeichenfolgen als Typen</span><span class="sxs-lookup"><span data-stu-id="954a8-111">Writing Strings as types</span></span>  

 <span data-ttu-id="954a8-112">Im folgenden Beispiel wird ein **Int32**-Typ gelesen und in eine Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="954a8-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="954a8-113">Die folgenden XML-Eingaben sind vorhanden:</span><span class="sxs-lookup"><span data-stu-id="954a8-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="954a8-114">**Eingabe**</span><span class="sxs-lookup"><span data-stu-id="954a8-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="954a8-115">Mit diesem Code wird der **Int32**-Typ in einen **String** konvertiert:</span><span class="sxs-lookup"><span data-stu-id="954a8-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="954a8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="954a8-116">See also</span></span>

- [<span data-ttu-id="954a8-117">Konvertieren von Zeichenfolgen in .NET Framework-Datentypen</span><span class="sxs-lookup"><span data-stu-id="954a8-117">Converting Strings to .NET Framework Data Types</span></span>](converting-strings-to-dotnet-data-types.md)
- [<span data-ttu-id="954a8-118">Konvertieren von .NET Framework-Typen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="954a8-118">Converting .NET Framework Types to Strings</span></span>](converting-dotnet-types-to-strings.md)
