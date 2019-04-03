---
title: Auf "<name>" kann nicht verwiesen werden, da es ein Member des auf Werttypen basierenden Felds "<name>" der Klasse "<classname>" ist, die "System.MarshalByRefObject" als Basisklasse hat.
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: aac190119ced74496c4dd012d200fca6d895ff28
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826768"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a><span data-ttu-id="ebaa8-102">Kann nicht auf verweisen "\<Name >', da es sich um ein Mitglied der Werttypen basierenden Felds ist"\<Name > "der Klasse\<Klassenname >" die "System.MarshalByRefObject" als Basisklasse hat</span><span class="sxs-lookup"><span data-stu-id="ebaa8-102">Cannot refer to '\<name>' because it is a member of the value-typed field '\<name>' of class '\<classname>' which has 'System.MarshalByRefObject' as a base class</span></span>
<span data-ttu-id="ebaa8-103">Die `System.MarshalByRefObject` -Klasse ermöglicht es Anwendungen, die remote-Zugriff auf Objekte über Anwendungsdomänen hinweg zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="ebaa8-104">Typen müssen erben von der `MarshalByRejectObject` Klasse, wenn der Typ über Anwendungsdomänengrenzen hinweg verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="ebaa8-105">Der Zustand des Objekts muss nicht kopiert werden, da die Member des Objekts nicht außerhalb der Anwendungsdomäne verwendet werden, in denen sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="ebaa8-106">**Fehler-ID:** BC30310</span><span class="sxs-lookup"><span data-stu-id="ebaa8-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ebaa8-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ebaa8-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="ebaa8-108">Überprüfen Sie den Verweis auf die Stellen Sie sicher, dass das Element verwiesen wird, gültig ist.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="ebaa8-109">Qualifizieren Sie explizit das Element mit dem `Me` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="ebaa8-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebaa8-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebaa8-110">See also</span></span>

- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="ebaa8-111">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ebaa8-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
