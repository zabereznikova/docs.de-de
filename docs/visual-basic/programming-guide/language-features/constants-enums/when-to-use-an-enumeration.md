---
title: Situationen für die Verwendung von Enumerationen
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: ba69249e16b8c0ee06d57d06d192874a283b295e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403536"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="7d7a8-102">Situationen für die Verwendung von Enumerationen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d7a8-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="7d7a8-103">Enumerationen bieten eine einfache Möglichkeit, mit Sätzen verwandter Konstanten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="7d7a8-104">Eine Enumeration, oder `Enum` , ist ein symbolischer Name für einen Satz von Werten.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="7d7a8-105">Enumerationen werden als Datentypen behandelt, und Sie können Sie zum Erstellen von Konstanten für die Verwendung mit Variablen und Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="7d7a8-106">Situationen für die Verwendung von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d7a8-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="7d7a8-107">Wenn eine Prozedur einen begrenzten Satz an Variablen akzeptiert, sollten Sie die Verwendung einer Enumeration in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="7d7a8-108">Enumerationen sorgen für klareren und besser lesbaren Code, insbesondere dann, wenn aussagekräftige Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="7d7a8-109">Zu den Vorteilen der Verwendung von Enumerationen gehören:</span><span class="sxs-lookup"><span data-stu-id="7d7a8-109">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="7d7a8-110">Reduziert Fehler, die durch das übertragen oder falsch formatiping von Zahlen verursacht werden</span><span class="sxs-lookup"><span data-stu-id="7d7a8-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="7d7a8-111">Erleichtert das Ändern von Werten in der Zukunft.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-111">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="7d7a8-112">Vereinfacht das Lesen von Code, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler in das Skript einfließen.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="7d7a8-113">Gewährleistet die Vorwärtskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-113">Ensures forward compatibility.</span></span> <span data-ttu-id="7d7a8-114">Mit Enumerationen schlägt der Code weniger wahrscheinlich fehl, wenn Sie in Zukunft die Werte ändern, die den Elementnamen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="7d7a8-115">Benennen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d7a8-115">Naming Enumerations</span></span>  
 <span data-ttu-id="7d7a8-116">Verwenden Sie eine Benennungs Konvention für Enumerationsmember.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="7d7a8-117">Wenn Visual Basic auf einen enumerationselementnamen stößt, wird möglicherweise eine Ausnahme ausgelöst, wenn andere Typbibliotheken, auf die verwiesen wird, denselben Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="7d7a8-118">Verwenden Sie ein eindeutiges Präfix, das die Werte aus der Anwendung oder Komponente identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="7d7a8-119">Wenn Sie auf einen Member einer Enumeration verweisen, müssen Sie den Elementnamen mit dem Namen der Enumeration qualifizieren oder die `Imports` Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="7d7a8-120">Weitere Informationen finden Sie unter [Enumerationen und namens Qualifizierung](enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="7d7a8-120">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="7d7a8-121">Vordefinierte Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d7a8-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="7d7a8-122">Visual Basic bietet eine Reihe vordefinierter Enumerationen, wie z `FirstDayOfWeek` `MsgBoxResult` . b. und, um Ihren Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7d7a8-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="7d7a8-123">Eine Liste dieser Informationen finden Sie unter [Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="7d7a8-123">For a list of these see [Constants and Enumerations](../../../language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7a8-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d7a8-124">See also</span></span>

- [<span data-ttu-id="7d7a8-125">Gewusst wie: Deklarieren einer Enumeration</span><span class="sxs-lookup"><span data-stu-id="7d7a8-125">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="7d7a8-126">Vorgehensweise: Verweisen auf einen Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="7d7a8-126">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="7d7a8-127">Enumerationen und Namensqualifikation</span><span class="sxs-lookup"><span data-stu-id="7d7a8-127">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="7d7a8-128">Gewusst wie: Durchlaufen einer Enumeration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d7a8-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="7d7a8-129">Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7d7a8-129">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="7d7a8-130">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7d7a8-130">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
- [<span data-ttu-id="7d7a8-131">Konstanten und Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7d7a8-131">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
