---
title: Nullbasierter und 1-basierter Zeichenfolgenzugriff
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 91d3fb9d7bfdf3d5af27fc6499583640946a802f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072287"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>Nullbasierter und 1-basierter Zeichenfolgenzugriff in Visual Basic

In diesem Thema wird erläutert, wie Visual Basic und die .NET Framework Zugriff auf die Zeichen in einer Zeichenfolge bereitstellen. Der-.NET Framework bietet stets NULL basierten Zugriff auf die Zeichen in einer Zeichenfolge, während Visual Basic einen NULL basierten und 1-basierten Zugriff bereitstellt, abhängig von der Funktion.  
  
## <a name="one-based"></a>Einbasiert  

 Ein Beispiel für eine einbasierte Visual Basic Funktion ist die- `Mid` Funktion. Es wird ein Argument verwendet, das die Zeichenposition angibt, an der die Teil Zeichenfolge beginnt, beginnend mit Position 1. Die .NET Framework- <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode nimmt einen Index des Zeichens in der Zeichenfolge an, an der die Teil Zeichenfolge beginnt, beginnend mit Position 0. Wenn Sie also über eine Zeichenfolge "abcde" verfügen, werden die einzelnen Zeichen 1, 2, 3, 4, 5 für die Verwendung mit der- `Mid` Funktion, aber 0, 1, 2, 3, 4 zur Verwendung mit der- <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode nummeriert.  
  
## <a name="zero-based"></a>Null basiert  

 Ein Beispiel für eine Null basierte Visual Basic Funktion ist die- `Split` Funktion. Sie teilt eine Zeichenfolge und gibt ein Array zurück, das die Teil Zeichenfolgen enthält. Die .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> -Methode teilt auch eine Zeichenfolge auf und gibt ein Array mit den Teil Zeichenfolgen zurück. Da die `Split` Funktion und die <xref:System.String.Split%2A> Methode .NET Framework Arrays zurückgeben, müssen Sie NULL basiert sein.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [Einführung in Zeichenfolgen in Visual Basic](introduction-to-strings.md)
