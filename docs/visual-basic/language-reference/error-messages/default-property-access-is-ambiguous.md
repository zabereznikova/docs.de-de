---
title: Zugriff auf die Standardeigenschaft ist mehrdeutig zwischen die geerbten Schnittstellenmember &#39; &lt;Defaultpropertyname&gt;&#39; Schnittstelle &#39;&lt; schnittstellenname1&gt;&#39; und &#39;&lt; Defaultpropertyname&gt;&#39; Schnittstelle &#39;&lt; schnittstellenname2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords: BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23d613668ee2d92484117759dd614ed2cad4bcb2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename1gt39-and-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename2gt39"></a><span data-ttu-id="dcff6-102">Zugriff auf die Standardeigenschaft ist mehrdeutig zwischen die geerbten Schnittstellenmember &#39; &lt;Defaultpropertyname&gt;&#39; Schnittstelle &#39;&lt; schnittstellenname1&gt;&#39; und &#39;&lt; Defaultpropertyname&gt;&#39; Schnittstelle &#39;&lt; schnittstellenname2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="dcff6-102">Default property access is ambiguous between the inherited interface members &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename1&gt;&#39; and &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename2&gt;&#39;</span></span>
<span data-ttu-id="dcff6-103">Eine Schnittstelle erbt von zwei Schnittstellen, von die jede eine Standardeigenschaft mit demselben Namen deklariert.</span><span class="sxs-lookup"><span data-stu-id="dcff6-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="dcff6-104">Der Compiler kann keinen Zugriff auf diese Eigenschaft standardmäßig ohne Qualifizierung aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="dcff6-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="dcff6-105">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dcff6-105">The following example illustrates this.</span></span>  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="dcff6-106">Geben Sie bei `testObj(1)`, versucht der Compiler, es in die Standardeigenschaft aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="dcff6-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="dcff6-107">Es gibt jedoch zwei möglichen Standardeigenschaften aufgrund der geerbten Schnittstellen, damit der Compiler diesen Fehler signalisiert.</span><span class="sxs-lookup"><span data-stu-id="dcff6-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>  
  
 <span data-ttu-id="dcff6-108">**Fehler-ID:** BC30686</span><span class="sxs-lookup"><span data-stu-id="dcff6-108">**Error ID:** BC30686</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dcff6-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="dcff6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="dcff6-110">Vermeiden Sie erbt alle Member mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="dcff6-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="dcff6-111">Im vorherigen Beispiel wenn `testObj` benötigt keine von, z. B. `Iface2`, deklarieren Sie es wie folgt:</span><span class="sxs-lookup"><span data-stu-id="dcff6-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     <span data-ttu-id="dcff6-112">- oder - </span><span class="sxs-lookup"><span data-stu-id="dcff6-112">-or-</span></span>  
  
-   <span data-ttu-id="dcff6-113">Implementieren Sie die erbende Schnittstelle in einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="dcff6-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="dcff6-114">Anschließend können Sie jede der geerbten Eigenschaften mit unterschiedlichen Namen implementieren.</span><span class="sxs-lookup"><span data-stu-id="dcff6-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="dcff6-115">Allerdings kann nur eine davon die Standardeigenschaft der implementierenden Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="dcff6-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="dcff6-116">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dcff6-116">The following example illustrates this.</span></span>  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dcff6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcff6-117">See Also</span></span>  
 [<span data-ttu-id="dcff6-118">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dcff6-118">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
