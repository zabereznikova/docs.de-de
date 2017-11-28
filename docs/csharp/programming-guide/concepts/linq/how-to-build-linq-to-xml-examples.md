---
title: 'Vorgehensweise: Erstellen von LINQ to XML-Beispielen (C#)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8df8555f587714834b2c444f3455d505a39dac02
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-build-linq-to-xml-examples-c"></a><span data-ttu-id="6e09a-102">Vorgehensweise: Erstellen von LINQ to XML-Beispielen (C#)</span><span class="sxs-lookup"><span data-stu-id="6e09a-102">How to: Build LINQ to XML Examples (C#)</span></span>
<span data-ttu-id="6e09a-103">Die verschiedenen Ausschnitte und Beispiele in dieser Dokumentation verwenden Klassen und Typen aus verschiedenen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="6e09a-103">The various snippets and examples in this documentation use classes and types from a variety of namespaces.</span></span> <span data-ttu-id="6e09a-104">Beim Kompilieren von C#-Code müssen Sie entsprechende `using`-Direktiven angeben.</span><span class="sxs-lookup"><span data-stu-id="6e09a-104">When compiling C# code, you need to supply appropriate `using` directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e09a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e09a-105">Example</span></span>  
 <span data-ttu-id="6e09a-106">Der folgende Code enthält die von den C#-Beispielen zum Erstellen und Ausführen benötigten `using`-Direktiven.</span><span class="sxs-lookup"><span data-stu-id="6e09a-106">The following code contains the `using` directives that the C# examples require to build and run.</span></span> <span data-ttu-id="6e09a-107">Nicht alle `using`-Direktiven sind für jedes Beispiel erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e09a-107">Not all `using` directives are required for every example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6e09a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e09a-108">See Also</span></span>  
 [<span data-ttu-id="6e09a-109">LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="6e09a-109">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
