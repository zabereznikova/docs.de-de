---
title: Der Standardeigenschaftenzugriff ist nicht eindeutig. Es kann sich um den geerbten Schnittstellenmember '<defaultpropertyname>' der Schnittstelle '<interfacename1>' oder '<defaultpropertyname>' der Schnittstelle '<interfacename2>' handeln.
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: a36cfe8e5496bbfd1941afa8a46086491ae96a2a
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512749"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a><span data-ttu-id="8d13d-102">Zugriff auf die Standardeigenschaft ist mehrdeutig zwischen den geerbten Schnittstellenmember\<Defaultpropertyname > 'der Schnittstelle'\<schnittstellenname1 >' und '\<Defaultpropertyname > 'der Schnittstelle'\< schnittstellenname2 >'</span><span class="sxs-lookup"><span data-stu-id="8d13d-102">Default property access is ambiguous between the inherited interface members '\<defaultpropertyname>' of interface '\<interfacename1>' and '\<defaultpropertyname>' of interface '\<interfacename2>'</span></span>

<span data-ttu-id="8d13d-103">Eine Schnittstelle erbt von zwei Schnittstellen, von denen jede eine Standard Eigenschaft mit demselben Namen deklariert.</span><span class="sxs-lookup"><span data-stu-id="8d13d-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="8d13d-104">Der Compiler kann keinen Zugriff auf diese Standard Eigenschaft ohne Qualifizierung auflösen.</span><span class="sxs-lookup"><span data-stu-id="8d13d-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="8d13d-105">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8d13d-105">The following example illustrates this.</span></span>

```vb
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

<span data-ttu-id="8d13d-106">Wenn Sie angeben `testObj(1)`, versucht der Compiler, ihn in die Default-Eigenschaft aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="8d13d-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="8d13d-107">Aufgrund der geerbten Schnittstellen gibt es jedoch zwei mögliche Standardeigenschaften, daher signalisiert der Compiler diesen Fehler.</span><span class="sxs-lookup"><span data-stu-id="8d13d-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>

<span data-ttu-id="8d13d-108">**Fehler-ID:** BC30686</span><span class="sxs-lookup"><span data-stu-id="8d13d-108">**Error ID:** BC30686</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8d13d-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8d13d-109">To correct this error</span></span>

- <span data-ttu-id="8d13d-110">Vermeiden Sie das Erben von Membern mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="8d13d-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="8d13d-111">Wenn `testObj` im vorherigen Beispiel keines der Member von `Iface2`benötigt, z. b.,, deklarieren Sie es wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8d13d-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>

  ```vb
  Dim testObj As Iface1
  ```

  <span data-ttu-id="8d13d-112">\- oder -</span><span class="sxs-lookup"><span data-stu-id="8d13d-112">\-or-</span></span>

- <span data-ttu-id="8d13d-113">Implementieren Sie die erbende Schnittstelle in einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="8d13d-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="8d13d-114">Anschließend können Sie jede der geerbten Eigenschaften mit unterschiedlichen Namen implementieren.</span><span class="sxs-lookup"><span data-stu-id="8d13d-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="8d13d-115">Es kann jedoch nur eine der Standardeigenschaften der implementierenden Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="8d13d-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="8d13d-116">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8d13d-116">The following example illustrates this.</span></span>

  ```vb
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

## <a name="see-also"></a><span data-ttu-id="8d13d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d13d-117">See also</span></span>

- [<span data-ttu-id="8d13d-118">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8d13d-118">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
