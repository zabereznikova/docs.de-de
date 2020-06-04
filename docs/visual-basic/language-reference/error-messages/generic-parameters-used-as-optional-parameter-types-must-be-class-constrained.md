---
title: Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 273ea592e73be5d76a4ffef077e691014a108347
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402926"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="ea633-102">Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ea633-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="ea633-103">Eine Prozedur wird mit einem optionalen Parameter deklariert, der einen Typparameter verwendet, der nicht als Referenztyp beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="ea633-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="ea633-104">Sie müssen immer einen Standardwert für jeden optionalen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="ea633-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="ea633-105">Wenn der-Parameter ein Verweistyp ist, muss der optionale Wert lauten `Nothing` . Dies ist ein gültiger Wert für einen beliebigen Verweistyp.</span><span class="sxs-lookup"><span data-stu-id="ea633-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="ea633-106">Wenn es sich bei dem Parameter jedoch um einen Werttyp handelt, muss es sich bei dem Typ um einen vom Visual Basic vordefinierten elementaren Datentyp handeln.</span><span class="sxs-lookup"><span data-stu-id="ea633-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="ea633-107">Dies liegt daran, dass ein zusammengesetzter Werttyp, z. b. eine benutzerdefinierte Struktur, über keinen gültigen Standardwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="ea633-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="ea633-108">Wenn Sie einen Typparameter für einen optionalen Parameter verwenden, müssen Sie sicherstellen, dass es sich um einen Verweistyp handelt, um die Möglichkeit eines Werttyps ohne gültigen Standardwert zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="ea633-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="ea633-109">Dies bedeutet, dass Sie den Typparameter entweder mit dem- `Class` Schlüsselwort oder mit dem Namen einer bestimmten Klasse einschränken müssen.</span><span class="sxs-lookup"><span data-stu-id="ea633-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="ea633-110">**Fehler-ID:** BC32124</span><span class="sxs-lookup"><span data-stu-id="ea633-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea633-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ea633-111">To correct this error</span></span>  
  
- <span data-ttu-id="ea633-112">Schränken Sie den Typparameter ein, um nur einen Verweistyp zu akzeptieren, oder verwenden Sie ihn nicht für den optionalen Parameter.</span><span class="sxs-lookup"><span data-stu-id="ea633-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea633-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea633-113">See also</span></span>

- [<span data-ttu-id="ea633-114">Generische Typen in Visual Basic (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea633-114">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="ea633-115">Type List</span><span class="sxs-lookup"><span data-stu-id="ea633-115">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="ea633-116">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ea633-116">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="ea633-117">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="ea633-117">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="ea633-118">Strukturen</span><span class="sxs-lookup"><span data-stu-id="ea633-118">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="ea633-119">Schweigen</span><span class="sxs-lookup"><span data-stu-id="ea633-119">Nothing</span></span>](../nothing.md)
