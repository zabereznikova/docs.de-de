---
title: 'Vorgehensweise: Behandeln einer Ausnahme mit „try/catch“ (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie eine Ausnahme mit einem try-catch-Block behandeln. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: 556f4459f5d1f8b7a7419122b640c661e182a51c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178657"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Vorgehensweise: Behandeln einer Ausnahme mit „try/catch“ (C#-Programmierleitfaden)

Ein [try/catch](../../language-reference/keywords/try-catch.md)-Block soll von Arbeitscode generierte Ausnahmen abfangen und verarbeiten. Einige Ausnahmen können in einem `catch`-Block verarbeitet werden, und das Problem kann behoben werden, ohne dass die Ausnahme erneut ausgelöst wird. Allerdings können Sie meistens nur sicherstellen, dass die passende Ausnahme ausgelöst wird.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel ist <xref:System.IndexOutOfRangeException> nicht die passendste Ausnahme: Für diese Methode ist <xref:System.ArgumentOutOfRangeException> sinnvoller, da der Fehler durch die Übergabe des Arguments `index` des Aufrufers verursacht wird.  
  
 [!code-csharp[csProgGuideExceptions#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#5)]  
  
## <a name="comments"></a>Kommentare  

 Der Code, der eine Ausnahme auslöst, ist im `try`-Block eingeschlossen. Eine `catch`-Anweisung wird direkt danach hinzugefügt, um `IndexOutOfRangeException` zu verarbeiten, falls dies auftritt. Der `catch`-Block verarbeitet `IndexOutOfRangeException` und löst stattdessen die passendere Ausnahme `ArgumentOutOfRangeException` aus. Um dem Aufrufer so viele Informationen wie möglich bereitzustellen, können Sie die ursprüngliche Ausnahme auf <xref:System.Exception.InnerException%2A> der neuen Ausnahme festlegen. Da die Eigenschaft <xref:System.Exception.InnerException%2A> [schreibgeschützt](../../properties.md#read-only) ist, müssen Sie sie im Konstruktor der neuen Ausnahme zuweisen.  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Ausnahmen und Ausnahmebehandlung](./index.md)
- [Ausnahmebehandlung](./exception-handling.md)
