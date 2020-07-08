---
title: Beispiele für Plattformaufrufe
description: Sehen Sie sich ein Beispiel für den Aufruf der Plattform an, das veranschaulicht, wie die MessageBox-Funktion in „User32.dll“ definiert und aufgerufen wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
ms.openlocfilehash: 97b0720b8954bc24a4058e6a03c32d32bd9e3180
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620806"
---
# <a name="platform-invoke-examples"></a>Beispiele für Plattformaufrufe
In den folgenden Beispielen erfahren Sie, wie Sie durch die Übergabe einer einfachen Zeichenfolge als Argument die Funktion **MessageBox** in der Datei „User32.dll“ definieren und aufrufen. In den Beispielen ist das Feld <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> auf **Auto** (Automatisch) festgelegt, damit die Zielplattform die Zeichenbreite und das Marshalling von Zeichenfolgen festlegen kann.  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)]
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)]
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 Weitere Beispiele finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mithilfe des Plattformaufrufs)](marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](creating-prototypes-in-managed-code.md)
- [Specifying a Character Set (Angeben eines Zeichensatzes)](specifying-a-character-set.md)
