---
title: <typename> ist ein Delegattyp
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4cc0a1221dcf65aa2a16fd7d82568c8544f27fdb
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875089"
---
# <a name="typename-is-a-delegate-type"></a><span data-ttu-id="a63e5-102">\<typename> ist ein Delegattyp</span><span class="sxs-lookup"><span data-stu-id="a63e5-102">'\<typename>' is a delegate type</span></span>

<span data-ttu-id="a63e5-103">" \<typename> " ist ein Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="a63e5-103">'\<typename>' is a delegate type.</span></span> <span data-ttu-id="a63e5-104">Bei der Delegatkonstruktion ist nur ein einzelner AddressOf-Ausdruck als Argumentliste zulässig.</span><span class="sxs-lookup"><span data-stu-id="a63e5-104">Delegate construction permits only a single AddressOf expression as an argument list.</span></span> <span data-ttu-id="a63e5-105">Häufig kann ein AddressOf-Ausdruck anstelle einer Delegaterstellung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a63e5-105">Often an AddressOf expression can be used instead of a delegate construction.</span></span>  
  
 <span data-ttu-id="a63e5-106">Eine- `New` Klausel, die eine Instanz einer Delegatklasse erstellt, stellt eine ungültige Argumentliste für den Delegatkonstruktor bereit.</span><span class="sxs-lookup"><span data-stu-id="a63e5-106">A `New` clause creating an instance of a delegate class supplies an invalid argument list to the delegate constructor.</span></span>  
  
 <span data-ttu-id="a63e5-107">Sie können nur einen einzelnen Ausdruck angeben, `AddressOf` Wenn Sie eine neue Delegatinstanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="a63e5-107">You can supply only a single `AddressOf` expression when creating a new delegate instance.</span></span>  
  
 <span data-ttu-id="a63e5-108">Dieser Fehler kann auftreten, wenn Sie keine Argumente an den Delegatkonstruktor übergeben, wenn Sie mehr als ein Argument übergeben oder wenn Sie ein einzelnes Argument übergeben, das kein gültiger Ausdruck ist `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="a63e5-108">This error can result if you do not pass any arguments to the delegate constructor, if you pass more than one argument, or if you pass a single argument that is not a valid `AddressOf` expression.</span></span>  
  
 <span data-ttu-id="a63e5-109">**Fehler-ID:** BC32008</span><span class="sxs-lookup"><span data-stu-id="a63e5-109">**Error ID:** BC32008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a63e5-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a63e5-110">To correct this error</span></span>  
  
- <span data-ttu-id="a63e5-111">Verwenden Sie einen einzelnen `AddressOf` Ausdruck in der Argumentliste für die Delegatklasse in der- `New` Klausel.</span><span class="sxs-lookup"><span data-stu-id="a63e5-111">Use a single `AddressOf` expression in the argument list for the delegate class in the `New` clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a63e5-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a63e5-112">See also</span></span>

- [<span data-ttu-id="a63e5-113">New-Operator</span><span class="sxs-lookup"><span data-stu-id="a63e5-113">New Operator</span></span>](../operators/new-operator.md)
- [<span data-ttu-id="a63e5-114">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="a63e5-114">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="a63e5-115">Delegaten</span><span class="sxs-lookup"><span data-stu-id="a63e5-115">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="a63e5-116">Vorgehensweise: Aufrufen einer Delegatenmethode</span><span class="sxs-lookup"><span data-stu-id="a63e5-116">How to: Invoke a Delegate Method</span></span>](../../programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
