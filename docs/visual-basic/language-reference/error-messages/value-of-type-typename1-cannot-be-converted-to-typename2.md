---
title: Der Wert vom Typ "<typename1>" kann nicht zu "<typename2>" konvertiert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: f6b35efbc445887c537b94dd299b317a28e5f689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406559"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="44923-102">Der Wert vom Typ "\<typename1>" kann nicht zu "\<typename2>" konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="44923-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>
<span data-ttu-id="44923-103">Der Wert vom Typ "" \<typename1> kann nicht in " \<typename2> " konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="44923-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="44923-104">Typen Konflikt kann durch das Mischen eines Datei Verweises mit einem Projekt Verweis auf die Assembly "" verursacht werden \<assemblyname> .</span><span class="sxs-lookup"><span data-stu-id="44923-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="44923-105">Ersetzen Sie den Datei Verweis auf " \<filepath> " im Projekt "" \<projectname1> durch einen Projekt Verweis auf " \<projectname2> ".</span><span class="sxs-lookup"><span data-stu-id="44923-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="44923-106">In einer Situation, in der ein Projekt sowohl einen Projekt Verweis als auch einen Datei Verweis erstellt, kann der Compiler nicht garantieren, dass ein Typ in einen anderen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="44923-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="44923-107">Der folgende Pseudo Code veranschaulicht eine Situation, in der dieser Fehler generiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="44923-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="44923-108">Project `P1` führt einen indirekten Projekt Verweis über Project `P2` to Project `P3` und auch einen direkten Datei Verweis auf aus `P3` .</span><span class="sxs-lookup"><span data-stu-id="44923-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="44923-109">In der Deklaration von `commonObject` wird der Datei Verweis auf verwendet `P3` , während der-Befehl von `P2.getCommonClass` den Projekt Verweis auf verwendet `P3` .</span><span class="sxs-lookup"><span data-stu-id="44923-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="44923-110">Das Problem in dieser Situation besteht darin, dass der Datei Verweis einen Dateipfad und-Namen für die Ausgabedatei von `P3` (in der Regel P3. dll) angibt, während die Projekt Verweise das Quell Projekt ( `P3` ) nach Projektname identifizieren.</span><span class="sxs-lookup"><span data-stu-id="44923-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="44923-111">Aus diesem Grund kann der Compiler nicht garantieren, dass der Typ `P3.commonClass` aus dem gleichen Quellcode durch die beiden unterschiedlichen Verweise stammt.</span><span class="sxs-lookup"><span data-stu-id="44923-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="44923-112">Diese Situation tritt in der Regel auf, wenn Projekt Verweise und Datei Verweise gemischt werden.</span><span class="sxs-lookup"><span data-stu-id="44923-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="44923-113">In der obigen Abbildung tritt das Problem nicht auf, wenn `P1` ein direkter Projekt Verweis auf `P3` anstelle eines Datei Verweises erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="44923-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="44923-114">**Fehler-ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="44923-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="44923-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="44923-115">To correct this error</span></span>  
  
- <span data-ttu-id="44923-116">Ändern Sie den Datei Verweis in einen Projekt Verweis.</span><span class="sxs-lookup"><span data-stu-id="44923-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44923-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44923-117">See also</span></span>

- [<span data-ttu-id="44923-118">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="44923-118">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="44923-119">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="44923-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
