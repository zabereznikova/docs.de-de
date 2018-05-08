---
title: Marshallen verschiedener Typen von Arrays
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed2a4b91608306021ce510098eaf044520cbb089
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="marshaling-different-types-of-arrays"></a>Marshallen verschiedener Typen von Arrays
Ein Array ist ein Verweistyp in verwaltetem Code, der ein oder mehrere Elemente des gleichen Typs enthält. Obwohl es sich bei Arrays um Verweistypen handelt, werden sie als In-Parameter an unverwaltete Funktionen übergeben. Dieses Verhalten entspricht nicht der Art und Weise, wie verwaltete Arrays an verwaltete Objekte übergeben werden, d. h. Als In-/Out-Parameter. Weitere Informationen finden Sie unter [kopieren und fixieren](copying-and-pinning.md).  
  
 Die folgende Tabelle enthält eine Liste der Marshallingoptionen für Arrays und beschreibt deren Verwendung.  
  
|Array|Beschreibung|  
|-----------|-----------------|  
|Aus ganzen Zahlen nach Wert|Übergibt ein aus ganzen Zahlen bestehendes Array als In-Parameter.|  
|Aus ganzen Zahlen nach Verweis|Übergibt ein aus ganzen Zahlen bestehendes Array als In-/Out-Parameter.|  
|Aus ganzen Zahlen nach Wert (zweidimensional)|Übergibt eine Matrix aus ganzen Zahlen als In-Parameter.|  
|Aus Zeichenfolgen nach Wert|Übergibt ein aus Zeichenfolgen bestehendes Array als In-Parameter.|  
|Aus Strukturen mit ganzen Zahlen|Übergibt ein aus Strukturen bestehendes Array mit ganzen Zahlen als In-Parameter.|  
|Aus Strukturen mit Zeichenfolgen|Übergibt ein aus Strukturen bestehendes Array, das nur ganze Zahlen enthält, als In-/Out-Parameter. Member des Arrays können geändert werden.|  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt, wie die folgenden Arraytypen übergeben werden:  
  
-   Array aus ganzen Zahlen nach Wert  
  
-   Array aus ganzen Zahlen nach Verweis, dessen Größe geändert werden kann  
  
-   Mehrdimensionales Array (Matrix) mit ganzen Zahlen nach Wert  
  
-   Array aus Zeichenfolgen nach Wert  
  
-   Array aus Strukturen mit ganzen Zahlen  
  
-   Array aus Strukturen mit Zeichenfolgen  
  
 Sofern ein Array nicht explizit nach Verweis gemarshallt wird, wird das Standardverhalten des Arrays als In-Parameter gemarshallt. Sie können dieses Verhalten ändern, indem Sie explizit die Attribute <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> anwenden.  
  
 Das Beispiel für Arrays verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:  
  
-   **TestArrayOfInts** aus PinvokeLib.dll exportiert.  
  
    ```  
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
-   **TestRefArrayOfInts** aus PinvokeLib.dll exportiert.  
  
    ```  
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
-   **TestMatrixOfInts** aus PinvokeLib.dll exportiert.  
  
    ```  
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
-   **TestArrayOfStrings** aus PinvokeLib.dll exportiert.  
  
    ```  
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
-   **TestArrayOfStructs** aus PinvokeLib.dll exportiert.  
  
    ```  
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
-   **TestArrayOfStructs2** aus PinvokeLib.dll exportiert.  
  
    ```  
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die Implementierungen für die zuvor aufgelisteten Funktionen und zwei Strukturvariablen enthält **MYPOINT** und **MYPERSON**. Die Strukturen enthalten die folgenden Elemente:  
  
```  
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
  
 Die `LibWrap`-Klasse enthält eine Reihe von Methoden, die von der `App`-Klasse aufgerufen werden. Spezifische Details zum Übergeben von Array finden Sie in den Kommentaren im folgenden Beispiel. Ein Array vom Typ "Verweis" wird standardmäßig als In-Parameter übergeben. Damit das aufrufende Programm die Ergebnisse erhält, müssen **InAttribute** und **OutAttribute** explizit dem Argument hinzugefügt werden, das das Array enthält.  
  
### <a name="declaring-prototypes"></a>Deklarieren von Prototypen  
 [!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)]
 [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]  
  
### <a name="calling-functions"></a>Aufrufen von Funktionen  
 [!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)]
 [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]  
  
## <a name="see-also"></a>Siehe auch  
 [Marshallen von Typenarrays](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))  
 [Datentypen für Plattformaufruf](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))  
 [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](creating-prototypes-in-managed-code.md)
