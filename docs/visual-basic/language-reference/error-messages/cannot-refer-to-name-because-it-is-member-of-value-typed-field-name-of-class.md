---
title: "Kann nicht auf verweisen &#39; &lt;Namen&gt;&#39; da es Mitglied der typisierte Wert Feld &#39; ist&lt; Namen&gt;&#39; Klasse &#39;&lt; Klassenname&gt;&#39; verfügt über &#39; System.MarshalByRefObject &#39; als Basisklasse"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords: BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a84811b9f0e706cf3ebede09e07c03bd7e4cea4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-refer-to-39ltnamegt39-because-it-is-a-member-of-the-value-typed-field-39ltnamegt39-of-class-39ltclassnamegt39-which-has-39systemmarshalbyrefobject39-as-a-base-class"></a><span data-ttu-id="9db40-102">Kann nicht auf verweisen &#39; &lt;Namen&gt;&#39; da es Mitglied der typisierte Wert Feld &#39; ist&lt; Namen&gt;&#39; Klasse &#39;&lt; Klassenname&gt;&#39; verfügt über &#39; System.MarshalByRefObject &#39; als Basisklasse</span><span class="sxs-lookup"><span data-stu-id="9db40-102">Cannot refer to &#39;&lt;name&gt;&#39; because it is a member of the value-typed field &#39;&lt;name&gt;&#39; of class &#39;&lt;classname&gt;&#39; which has &#39;System.MarshalByRefObject&#39; as a base class</span></span>
<span data-ttu-id="9db40-103">Die `System.MarshalByRefObject` -Klasse ermöglicht es Anwendungen, die remote-Zugriff auf Objekte über Anwendungsdomänengrenzen hinweg zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9db40-103">The `System.MarshalByRefObject` class enables applications that support remote access to objects across application domain boundaries.</span></span> <span data-ttu-id="9db40-104">Typen müssen von erben die `MarshalByRejectObject` Klasse, wenn der Typ über Anwendungsdomänengrenzen hinweg verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9db40-104">Types must inherit from the `MarshalByRejectObject` class when the type is used across application domain boundaries.</span></span> <span data-ttu-id="9db40-105">Der Zustand des Objekts muss nicht kopiert werden, da die Member des Objekts nicht außerhalb der Anwendungsdomäne verwendet werden, in denen sie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9db40-105">The state of the object must not be copied because the members of the object are not usable outside the application domain in which they were created.</span></span>  
  
 <span data-ttu-id="9db40-106">**Fehler-ID:** BC30310</span><span class="sxs-lookup"><span data-stu-id="9db40-106">**Error ID:** BC30310</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9db40-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9db40-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="9db40-108">Überprüfen Sie den Verweis, um sicherzustellen, dass das Element, auf die verwiesen wird, gültig ist.</span><span class="sxs-lookup"><span data-stu-id="9db40-108">Check the reference to make sure the member being referred to is valid.</span></span>  
  
2.  <span data-ttu-id="9db40-109">Explizit zu qualifizieren das Element mit dem `Me` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="9db40-109">Explicitly qualify the member with the `Me` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db40-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9db40-110">See Also</span></span>  
 <xref:System.MarshalByRefObject>  
 [<span data-ttu-id="9db40-111">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9db40-111">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
