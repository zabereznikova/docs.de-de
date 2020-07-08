---
title: Marshallen verschiedener Typen von Arrays
description: Marshallen Sie verschiedene Typen von Arrays, wie z. B. ganze Zahlen nach Wert oder Verweis, zweidimensionale ganze Zahlen nach Wert, Zeichenfolgen nach Wert und Strukturen mit ganzen Zahlen oder Zeichenfolgen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
ms.openlocfilehash: f1473c7917189f0b36c96b2adcf20005c5fd6b48
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621495"
---
# <a name="marshaling-different-types-of-arrays"></a>Marshallen verschiedener Typen von Arrays
Ein Array ist ein Verweistyp in verwaltetem Code, der ein oder mehrere Elemente des gleichen Typs enthält. Obwohl es sich bei Arrays um Verweistypen handelt, werden sie als In-Parameter an unverwaltete Funktionen übergeben. Dieses Verhalten entspricht nicht der Art und Weise, wie verwaltete Arrays an verwaltete Objekte übergeben werden, d. h. Als In-/Out-Parameter. Weitere Details finden Sie unter [Kopieren und Fixieren](copying-and-pinning.md).  
  
 Die folgende Tabelle enthält eine Liste der Marshallingoptionen für Arrays und beschreibt deren Verwendung.  
  
|Array|Beschreibung|  
|-----------|-----------------|  
|Aus ganzen Zahlen nach Wert|Übergibt ein aus ganzen Zahlen bestehendes Array als In-Parameter.|  
|Aus ganzen Zahlen nach Verweis|Übergibt ein aus ganzen Zahlen bestehendes Array als In-/Out-Parameter.|  
|Aus ganzen Zahlen nach Wert (zweidimensional)|Übergibt eine Matrix aus ganzen Zahlen als In-Parameter.|  
|Aus Zeichenfolgen nach Wert|Übergibt ein aus Zeichenfolgen bestehendes Array als In-Parameter.|  
|Aus Strukturen mit ganzen Zahlen|Übergibt ein aus Strukturen bestehendes Array mit ganzen Zahlen als In-Parameter.|  
|Aus Strukturen mit Zeichenfolgen|Übergibt ein aus Strukturen bestehendes Array, das nur Zeichenfolgen enthält, als In-/Out-Parameter. Member des Arrays können geändert werden.|  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie die folgenden Arraytypen übergeben werden:  
  
- Array aus ganzen Zahlen nach Wert  
  
- Array aus ganzen Zahlen nach Verweis, dessen Größe geändert werden kann  
  
- Mehrdimensionales Array (Matrix) mit ganzen Zahlen nach Wert  
  
- Array aus Zeichenfolgen nach Wert  
  
- Array aus Strukturen mit ganzen Zahlen  
  
- Array aus Strukturen mit Zeichenfolgen  
  
 Sofern ein Array nicht explizit nach Verweis gemarshallt wird, wird das Standardverhalten des Arrays als In-Parameter gemarshallt. Sie können dieses Verhalten ändern, indem Sie explizit die Attribute <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> anwenden.  
  
 Das Beispiel für Arrays verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:  
  
- **TestArrayOfInts** aus PinvokeLib.dll exportiert.  
  
    ```cpp
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
- **TestRefArrayOfInts** aus PinvokeLib.dll exportiert.  
  
    ```cpp
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
- **TestMatrixOfInts** aus PinvokeLib.dll exportiert.  
  
    ```cpp
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
- **TestArrayOfStrings** aus PinvokeLib.dll exportiert.  
  
    ```cpp
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
- **TestArrayOfStructs** aus PinvokeLib.dll exportiert.  
  
    ```cpp
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
- **TestArrayOfStructs2** aus PinvokeLib.dll exportiert.  
  
    ```cpp
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 [PinvokeLib.dll](marshaling-data-with-platform-invoke.md#pinvokelibdll) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die Implementierungen für die zuvor aufgelisteten Funktionen und zwei Strukturvariablen ( **MYPOINT** und **MYPERSON**) enthält. Die Strukturen enthalten die folgenden Elemente:  
  
```cpp
typedef struct _MYPOINT  
{  
   int x;
   int y;
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;
   char* last;
} MYPERSON;  
```  
  
 In diesem Beispiel enthalten die Strukturen `MyPoint` und `MyPerson` eingebettete Typen. Das <xref:System.Runtime.InteropServices.StructLayoutAttribute> -Attribut ist so eingerichtet, dass sichergestellt wird, dass die Member im Speicher sequenziell in der Reihenfolge ihres Erscheinens angeordnet sind.  
  
 Die `NativeMethods` -Klasse enthält eine Reihe von Methoden, die von der `App` -Klasse aufgerufen werden. Spezifische Details zum Übergeben von Array finden Sie in den Kommentaren im folgenden Beispiel. Ein Array vom Typ "Verweis" wird standardmäßig als In-Parameter übergeben. Damit das aufrufende Programm die Ergebnisse erhält, müssen **InAttribute** und **OutAttribute** explizit dem Argument hinzugefügt werden, das das Array enthält.  
  
### <a name="declaring-prototypes"></a>Deklarieren von Prototypen  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a>Aufrufen von Funktionen  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen für den Plattformaufruf](marshaling-data-with-platform-invoke.md#platform-invoke-data-types)
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](creating-prototypes-in-managed-code.md)
