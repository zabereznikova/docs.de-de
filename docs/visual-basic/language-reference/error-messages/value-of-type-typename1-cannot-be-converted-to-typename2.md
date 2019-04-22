---
title: Der Wert vom Typ '<typename1>' kann nicht zu '<typename2>' konvertiert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
ms.openlocfilehash: 5f313a43bc3a2f983dabbd45477d120fdb80d063
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58829022"
---
# <a name="value-of-type-typename1-cannot-be-converted-to-typename2"></a><span data-ttu-id="60394-102">Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 >'</span><span class="sxs-lookup"><span data-stu-id="60394-102">Value of type '\<typename1>' cannot be converted to '\<typename2>'</span></span>
<span data-ttu-id="60394-103">Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 >'.</span><span class="sxs-lookup"><span data-stu-id="60394-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="60394-104">{Typenkonflikt beim wird möglicherweise durch das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >'.</span><span class="sxs-lookup"><span data-stu-id="60394-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="60394-105">Den Dateiverweis, ersetzen Sie die "\<" FilePath ">" in Projekt "\<projektnamen1 >' mit einem Projektverweis auf"\<projektname2 > ".</span><span class="sxs-lookup"><span data-stu-id="60394-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="60394-106">In einer Situation, in denen ein Projekt sowohl einen Projektverweis als auch ein Dateiverweis erstellt, garantiert der Compiler nicht, dass es sich bei einem Typ in einen anderen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="60394-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="60394-107">Der folgende Pseudocode veranschaulicht eine Situation, die diesen Fehler verursachen kann.</span><span class="sxs-lookup"><span data-stu-id="60394-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
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
  
 <span data-ttu-id="60394-108">Projekt `P1` indirekte Projekt verweist auf Projekt `P2` Projekt `P3`, und auch einen direkten Verweis auf `P3`.</span><span class="sxs-lookup"><span data-stu-id="60394-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="60394-109">Die Deklaration von `commonObject` verwendet den Dateiverweis auf `P3`, während im Aufruf von `P2.getCommonClass` verwendet den Projektverweis `P3`.</span><span class="sxs-lookup"><span data-stu-id="60394-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="60394-110">Das Problem in diesem Fall ist, dass es sich bei der Dateiverweis gibt an, einen Pfad und Namen für die Ausgabedatei `P3` (normalerweise p3.dll), während die Projektverweise auf das Quellprojekt ermitteln (`P3`) nach Projektname.</span><span class="sxs-lookup"><span data-stu-id="60394-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="60394-111">Aus diesem Grund der Compiler nicht garantieren, dass den Typ `P3.commonClass` stammt aus der gleiche Quellcode über zwei unterschiedliche Verweise.</span><span class="sxs-lookup"><span data-stu-id="60394-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="60394-112">Diese Situation tritt in der Regel auf, wenn Projektverweise und Dateiverweise kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="60394-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="60394-113">In der vorhergehenden Abbildung können das Problem würde nicht auftreten, wenn `P1` vorgenommen einen direkten Projektverweis auf `P3` anstelle eines Dateiverweises.</span><span class="sxs-lookup"><span data-stu-id="60394-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="60394-114">**Fehler-ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="60394-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60394-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="60394-115">To correct this error</span></span>  
  
-   <span data-ttu-id="60394-116">Den Dateiverweis, einen Projektverweis zu ändern.</span><span class="sxs-lookup"><span data-stu-id="60394-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60394-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60394-117">See also</span></span>

- [<span data-ttu-id="60394-118">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60394-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="60394-119">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="60394-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
