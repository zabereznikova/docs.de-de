---
title: 'Vorgehensweise: Behandeln einer Ausnahme mit „try/catch“ (C#-Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: adfc53cbe4fd603ac3a6de6b9a0162320d5a2e19
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712285"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Vorgehensweise: Behandeln einer Ausnahme mit „try/catch“ (C#-Programmierleitfaden)
Ein [try/catch](../../language-reference/keywords/try-catch.md)-Block soll von Arbeitscode generierte Ausnahmen abfangen und verarbeiten. Einige Ausnahmen können in einem `catch`-Block verarbeitet werden, und das Problem kann behoben werden, ohne dass die Ausnahme erneut ausgelöst wird. Allerdings können Sie meistens nur sicherstellen, dass die passende Ausnahme ausgelöst wird.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel ist <xref:System.IndexOutOfRangeException> nicht die passendste Ausnahme: Für diese Methode ist <xref:System.ArgumentOutOfRangeException> sinnvoller, da der Fehler durch die Übergabe des Arguments `index` des Aufrufers verursacht wird.  
  
 [!code-csharp[csProgGuideExceptions#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#5)]  
  
## <a name="comments"></a>Kommentare  
 Der Code, der eine Ausnahme auslöst, ist im `try`-Block eingeschlossen. Eine `catch`-Anweisung wird direkt danach hinzugefügt, um `IndexOutOfRangeException` zu verarbeiten, falls dies auftritt. Der `catch`-Block verarbeitet `IndexOutOfRangeException` und löst stattdessen die passendere Ausnahme `ArgumentOutOfRangeException` aus. Um dem Aufrufer so viele Informationen wie möglich bereitzustellen, können Sie die ursprüngliche Ausnahme auf <xref:System.Exception.InnerException%2A> der neuen Ausnahme festlegen. Da die Eigenschaft <xref:System.Exception.InnerException%2A>[schreibgeschützt](../../language-reference/keywords/readonly.md) ist, müssen Sie sie im Konstruktor der neuen Ausnahme zuweisen.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Ausnahmen und Ausnahmebehandlung](./index.md)
- [Ausnahmebehandlung](./exception-handling.md)
