---
title: 'Vorgehensweise: Erstellen von LINQ to XML-Beispielen (C#)'
ms.date: 07/20/2015
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
ms.openlocfilehash: 289a13daed7e3c871156bf50c6fa04c113c0cd13
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141458"
---
# <a name="how-to-build-linq-to-xml-examples-c"></a><span data-ttu-id="fe066-102">Vorgehensweise: Erstellen von LINQ to XML-Beispielen (C#)</span><span class="sxs-lookup"><span data-stu-id="fe066-102">How to build LINQ to XML examples (C#)</span></span>
<span data-ttu-id="fe066-103">Die verschiedenen Ausschnitte und Beispiele in dieser Dokumentation verwenden Klassen und Typen aus verschiedenen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="fe066-103">The various snippets and examples in this documentation use classes and types from a variety of namespaces.</span></span> <span data-ttu-id="fe066-104">Beim Kompilieren von C#-Code müssen Sie entsprechende `using`-Direktiven angeben.</span><span class="sxs-lookup"><span data-stu-id="fe066-104">When compiling C# code, you need to supply appropriate `using` directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe066-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe066-105">Example</span></span>  
 <span data-ttu-id="fe066-106">Der folgende Code enthält die von den C#-Beispielen zum Erstellen und Ausführen benötigten `using`-Direktiven.</span><span class="sxs-lookup"><span data-stu-id="fe066-106">The following code contains the `using` directives that the C# examples require to build and run.</span></span> <span data-ttu-id="fe066-107">Nicht alle `using`-Direktiven sind für jedes Beispiel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fe066-107">Not all `using` directives are required for every example.</span></span>  
  
```csharp  
using System;  
using System.Diagnostics;  
using System.Collections;  
using System.Collections.Generic;  
using System.Collections.Specialized;  
using System.Text;  
using System.Linq;  
using System.Xml;  
using System.Xml.Linq;  
using System.Xml.Schema;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
using System.IO;  
using System.Threading;  
using System.Reflection;  
using System.IO.Packaging;  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe066-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe066-108">See also</span></span>

- [<span data-ttu-id="fe066-109">LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="fe066-109">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
