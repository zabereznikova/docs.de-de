---
title: Kann nicht auf verweisen &#39; &lt;Namen&gt; &#39; , da es sich um ein Mitglied der Werttypen basierenden Felds ist &#39; &lt;Namen&gt; &#39; Klasse &#39; &lt;Classname&gt; &#39;IValidator.h &#39;System.MarshalByRefObject&#39; als Basisklasse
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: a6298c3e0f5102397d5cc3f237a186598c6b5ecc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739296"
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a><span data-ttu-id="83b9c-102">Kann nicht auf verweisen &#39; &lt;Namen&gt; &#39; , da es sich um ein Mitglied der Werttypen basierenden Felds ist &#39; &lt;Namen&gt; &#39; Klasse &#39; &lt;Classname&gt; &#39;IValidator.h &#39;System.MarshalByRefObject&#39; als Basisklasse</span><span class="sxs-lookup"><span data-stu-id="83b9c-102">Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class</span></span>
<span data-ttu-id="83b9c-103">Die `System.MarshalByRefObject` -Klasse ermöglicht es Anwendungen, die remote-Zugriff auf Objekte über Anwendungsdomänen hinweg zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="83b9c-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="83b9c-104">Typen müssen erben von der `MarshalByRejectObject` Klasse, wenn der Typ über Anwendungsdomänengrenzen hinweg verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="83b9c-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="83b9c-105">Der Zustand des Objekts muss nicht kopiert werden, da die Member des Objekts nicht außerhalb der Anwendungsdomäne verwendet werden, in denen sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="83b9c-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="83b9c-106">**Fehler-ID:** BC30310</span><span class="sxs-lookup"><span data-stu-id="83b9c-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83b9c-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="83b9c-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="83b9c-108">Überprüfen Sie den Verweis auf die Stellen Sie sicher, dass das Element verwiesen wird, gültig ist.</span><span class="sxs-lookup"><span data-stu-id="83b9c-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="83b9c-109">Qualifizieren Sie explizit das Element mit dem `Me` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="83b9c-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b9c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83b9c-110">See also</span></span>
- <xref:System.MarshalByRefObject>
- [<span data-ttu-id="83b9c-111">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="83b9c-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
