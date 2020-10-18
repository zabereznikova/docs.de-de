---
title: Der Standardeigenschaftenzugriff ist nicht eindeutig. Es kann sich um den geerbten Schnittstellenmember "<defaultpropertyname>" der Schnittstelle "<interfacename1>" oder "<defaultpropertyname>" der Schnittstelle "<interfacename2>" handeln.
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: b7c4c9c75de1b3777f34a70470b89f323a5699f9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162062"
---
# <a name="bc30686-default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a><span data-ttu-id="8e14d-102">BC30686: der Standardeigenschaften Zugriff ist zwischen den geerbten Schnittstellenmembern ' \<defaultpropertyname> ' der-Schnittstelle ' \<interfacename1> ' und ' \<defaultpropertyname> ' der-Schnittstelle \<interfacename2> mehrdeutig.</span><span class="sxs-lookup"><span data-stu-id="8e14d-102">BC30686: Default property access is ambiguous between the inherited interface members '\<defaultpropertyname>' of interface '\<interfacename1>' and '\<defaultpropertyname>' of interface '\<interfacename2>'</span></span>

<span data-ttu-id="8e14d-103">Eine Schnittstelle erbt von zwei Schnittstellen, von denen jede eine Standard Eigenschaft mit demselben Namen deklariert.</span><span class="sxs-lookup"><span data-stu-id="8e14d-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="8e14d-104">Der Compiler kann keinen Zugriff auf diese Standard Eigenschaft ohne Qualifizierung auflösen.</span><span class="sxs-lookup"><span data-stu-id="8e14d-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="8e14d-105">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8e14d-105">The following example illustrates this.</span></span>

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

<span data-ttu-id="8e14d-106">Wenn Sie angeben `testObj(1)` , versucht der Compiler, ihn in die Default-Eigenschaft aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="8e14d-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="8e14d-107">Aufgrund der geerbten Schnittstellen gibt es jedoch zwei mögliche Standardeigenschaften, daher signalisiert der Compiler diesen Fehler.</span><span class="sxs-lookup"><span data-stu-id="8e14d-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>

<span data-ttu-id="8e14d-108">**Fehler-ID:** BC30686</span><span class="sxs-lookup"><span data-stu-id="8e14d-108">**Error ID:** BC30686</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="8e14d-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8e14d-109">To correct this error</span></span>

- <span data-ttu-id="8e14d-110">Vermeiden Sie das Erben von Membern mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="8e14d-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="8e14d-111">Wenn im vorherigen Beispiel keines der Member von benötigt, z. b., `testObj` `Iface2` , deklarieren Sie es wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8e14d-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>

  ```vb
  Dim testObj As Iface1
  ```

  <span data-ttu-id="8e14d-112">\- oder -</span><span class="sxs-lookup"><span data-stu-id="8e14d-112">\-or-</span></span>

- <span data-ttu-id="8e14d-113">Implementieren Sie die erbende Schnittstelle in einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="8e14d-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="8e14d-114">Anschließend können Sie jede der geerbten Eigenschaften mit unterschiedlichen Namen implementieren.</span><span class="sxs-lookup"><span data-stu-id="8e14d-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="8e14d-115">Es kann jedoch nur eine der Standardeigenschaften der implementierenden Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="8e14d-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="8e14d-116">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8e14d-116">The following example illustrates this.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8e14d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e14d-117">See also</span></span>

- [<span data-ttu-id="8e14d-118">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8e14d-118">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
