---
title: NULL basierter und einbasierter Zeichen folgen Zugriff
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 97e60038bc7ec0f030939d0980b786bffebcfb9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354298"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Nullbasierter und 1-basierter Zeichenfolgenzugriff in Visual Basic
In diesem Thema wird erläutert, wie Visual Basic und die .NET Framework Zugriff auf die Zeichen in einer Zeichenfolge bereitstellen. Der-.NET Framework bietet stets NULL basierten Zugriff auf die Zeichen in einer Zeichenfolge, während Visual Basic einen NULL basierten und 1-basierten Zugriff bereitstellt, abhängig von der Funktion.  
  
## <a name="one-based"></a>Einbasiert  
 Ein Beispiel für eine einbasierte Visual Basic Funktion finden Sie in der `Mid`-Funktion. Es wird ein Argument verwendet, das die Zeichenposition angibt, an der die Teil Zeichenfolge beginnt, beginnend mit Position 1. Die .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType>-Methode nimmt einen Index des Zeichens in der Zeichenfolge an, an der die Teil Zeichenfolge beginnt, beginnend mit Position 0. Wenn Sie also über eine Zeichenfolge "abcde" verfügen, werden die einzelnen Zeichen 1, 2, 3, 4, 5 für die Verwendung mit der `Mid`-Funktion, aber 0, 1, 2, 3, 4 für die Verwendung mit der <xref:System.String.Substring%2A?displayProperty=nameWithType>-Methode nummeriert.  
  
## <a name="zero-based"></a>Null basiert  
 Wenn Sie ein Beispiel für eine Null basierte Visual Basic Funktion haben, sollten Sie die `Split`-Funktion in Erwägung gezogen. Sie teilt eine Zeichenfolge und gibt ein Array zurück, das die Teil Zeichenfolgen enthält. Die .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> Methode teilt auch eine Zeichenfolge auf und gibt ein Array zurück, das die Teil Zeichenfolgen enthält. Da die `Split` Funktion und <xref:System.String.Split%2A> Methode .NET Framework Arrays zurückgeben, müssen Sie NULL basiert sein.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
