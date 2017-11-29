---
title: Ein Wert vom Typ &#39; &lt;Typname1&gt;&#39; kann nicht konvertiert werden, um &#39;&lt; Typname2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
helpviewer_keywords: BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2154a56f9ff004f906cb2b571f8771e74cfca9c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a><span data-ttu-id="a883f-102">Ein Wert vom Typ &#39; &lt;Typname1&gt;&#39; kann nicht konvertiert werden, um &#39;&lt; Typname2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="a883f-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="a883f-103">Wert vom Typ "\<Typname1 >' kann nicht konvertiert werden, um"\<Typname2 > ".</span><span class="sxs-lookup"><span data-stu-id="a883f-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="a883f-104">Typenkonflikt möglicherweise zurückzuführen. das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >'.</span><span class="sxs-lookup"><span data-stu-id="a883f-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="a883f-105">Ersetzen Sie den Dateiverweis auf "\<Filepath >" in Projekt "\<projektname1 >" mit einem Projektverweis auf "\<projektname2 >".</span><span class="sxs-lookup"><span data-stu-id="a883f-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="a883f-106">In einer Situation, in denen ein Projekt einen Projektverweis und ein Dateiverweis erstellt, kann der Compiler nicht garantieren, einem Typ in einen anderen konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a883f-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="a883f-107">Der folgende Pseudocode veranschaulicht eine Situation, die dieser Fehler generiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a883f-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
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
  
 <span data-ttu-id="a883f-108">Projekt `P1` macht einen indirekten Projektverweis über Projekt `P2` Projekt `P3`, und auch einen direkten Dateiverweis auf `P3`.</span><span class="sxs-lookup"><span data-stu-id="a883f-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="a883f-109">Die Deklaration von `commonObject` verwendet den Dateiverweis auf `P3`, während im Aufruf von `P2.getCommonClass` verwendet den Projektverweis `P3`.</span><span class="sxs-lookup"><span data-stu-id="a883f-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="a883f-110">Das Problem in diesem Fall ist, dass das Projekt einen Dateipfad und einen Namen für die Ausgabedatei gibt `P3` (normalerweise p3.dll), während das Projekt verweist auf das Quellprojekt ermitteln (`P3`) durch den Namen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="a883f-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="a883f-111">Aus diesem Grund der Compiler nicht garantieren, dass den Typ `P3.commonClass` stammen aus dem gleichen Quellcode über zwei unterschiedliche Verweise.</span><span class="sxs-lookup"><span data-stu-id="a883f-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="a883f-112">Diese Situation tritt in der Regel auf, wenn Projektverweise und Dateiverweise gemischt werden.</span><span class="sxs-lookup"><span data-stu-id="a883f-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="a883f-113">In der vorherigen Abbildung sind das Problem würde nicht auftreten, wenn `P1` mit einen direkten Projektverweis vorgenommen `P3` anstelle eines Dateiverweises.</span><span class="sxs-lookup"><span data-stu-id="a883f-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="a883f-114">**Fehler-ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="a883f-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a883f-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a883f-115">To correct this error</span></span>  
  
-   <span data-ttu-id="a883f-116">Den Dateiverweis auf einen Projektverweis zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a883f-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a883f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a883f-117">See Also</span></span>  
 [<span data-ttu-id="a883f-118">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a883f-118">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="a883f-119">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="a883f-119">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="a883f-120">NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweis hinzufügen"</span><span class="sxs-lookup"><span data-stu-id="a883f-120">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)
