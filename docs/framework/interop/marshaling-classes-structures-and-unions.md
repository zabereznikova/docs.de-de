---
title: Marshallen von Klassen, Strukturen und Unions
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc7141bb8fce5d5e1c2420a48d6081fa89aa0d53
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="marshaling-classes-structures-and-unions"></a>Marshallen von Klassen, Strukturen und Unions
Klassen und Strukturen sind in .NET Framework ähnlich. Beide können Felder, Eigenschaften und Ereignisse enthalten. Sie können auch über statische und nicht statische Methoden verfügen. Ein deutlicher Unterschied ist, dass Strukturen Werttypen sind, während Klassen Verweistypen sind.  
  
 In der folgende Tabelle werden Marshallingoptionen für Klassen, Strukturen und Unions aufgelistet. Ihre Verwendung wird beschrieben, und es werden Links zu den entsprechenden Plattformaufrufbeispielen bereitgestellt.  
  
|Typ|Beschreibung|Beispiel|  
|----------|-----------------|------------|  
|Klasse als Wert.|Übergibt eine Klasse mit ganzzahligen Membern als In/Out-Parameter, wie der verwaltete Fall.|SysTime-Beispiel|  
|Struktur als Wert.|Übergibt Strukturen als In-Parameter.|Beispiel für Strukturen|  
|Struktur als Verweis.|Übergibt Strukturen als In/Out-Parameter.|OSInfo-Beispiel|  
|Struktur mit geschachtelten Strukturen (vereinfacht).|Übergibt eine Klasse, die eine Struktur mit geschachtelten Strukturen in der nicht verwalteten Funktion darstellt. Die Struktur wird zu einer einzigen großen Struktur im verwalteten Prototyp vereinfacht.|FindFile-Beispiel|  
|Struktur mit einem Zeiger auf eine andere Struktur.|Übergibt eine Struktur, die einen Zeiger auf eine zweite Struktur enthält, als Member.|Beispiel für Strukturen|  
|Array von Strukturen mit ganzen Zahlen als Wert.|Übergibt ein Array von Strukturen, die nur ganze Zahlen enthalten, als In/Out-Parameter. Member des Arrays können geändert werden.|Beispiel zu Arrays|  
|Array von Strukturen mit ganzen Zahlen und Zeichenfolgen als Verweis.|Übergibt ein Array von Strukturen, die ganze Zahlen und Zeichenfolgen enthalten, als Out-Parameter. Die aufgerufene Funktion weist Speicher für das Array zu.|OutArrayOfStructs-Beispiel|  
|Unions mit Werttypen.|Übergibt Unions mit Werttypen (Integer und Double).|Unions-Beispiel|  
|Unions mit gemischten Typen.|Übergibt Unions mit gemischten Typen (Integer und String).|Unions-Beispiel|  
|Nullwerte in Struktur.|Übergibt einen NULL-Verweis (**Nothing** in Visual Basic) anstelle eines Verweises auf einen Werttyp.|HandleRef-Beispiel|  
  
## <a name="structures-sample"></a>Beispiel für Strukturen  
 Dieses Beispiel veranschaulicht das Übergeben einer Struktur, die auf eine zweite Struktur zeigt, einer Struktur mit einer eingebetteten Struktur sowie einer Struktur mit einem eingebetteten Array.  
  
 Das Beispiel für Strukturen verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:  
  
-   **TestStructInStruct** aus „PinvokeLib.dll“ exportiert.  
  
    ```  
    int TestStructInStruct(MYPERSON2* pPerson2);  
    ```  
  
-   **TestStructInStruct3** aus „PinvokeLib.dll“ exportiert.  
  
    ```  
    void TestStructInStruct3(MYPERSON3 person3);  
    ```  
  
-   **TestStructInStruct** aus „PinvokeLib.dll“ exportiert.  
  
    ```  
    void TestArrayInStruct( MYARRAYSTRUCT* pStruct );  
    ```  
  
 [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die Implementierungen für die zuvor aufgelisteten Funktionen und vier Strukturen enthält: **MYPERSON**, **MYPERSON2**, **MYPERSON3** und **MYARRAYSTRUCT**. Diese Strukturen enthalten die folgenden Elemente:  
  
```  
typedef struct _MYPERSON  
{  
   char* first;   
   char* last;   
} MYPERSON, *LP_MYPERSON;  
  
typedef struct _MYPERSON2  
{  
   MYPERSON* person;  
   int age;   
} MYPERSON2, *LP_MYPERSON2;  
  
typedef struct _MYPERSON3  
{  
   MYPERSON person;  
   int age;   
} MYPERSON3;  
  
typedef struct _MYARRAYSTRUCT  
{  
   bool flag;  
   int vals[ 3 ];   
} MYARRAYSTRUCT;  
```  
  
 Die verwalteten Strukturen `MyPerson`, `MyPerson2`, `MyPerson3` und `MyArrayStruct` besitzen folgende Eigenschaften:  
  
-   `MyPerson` enthält nur Zeichenfolgenmember. Das [CharSet](specifying-a-character-set.md)-Feld legt die Zeichenfolgen auf das ANSI-Format fest, wenn sie an die nicht verwaltete Funktion übergeben werden.  
  
-   `MyPerson2` enthält eine **IntPtr** in der `MyPerson`-Struktur. Der **IntPtr**-Typ ersetzt den ursprünglichen Zeiger auf die nicht verwaltete Struktur, weil .NET Framework-Anwendungen nur dann Zeiger verwenden, wenn der Code als **unsicher** gekennzeichnet ist.  
  
-   `MyPerson3` enthält `MyPerson` als eingebettete Struktur. Eine in eine Struktur eingebettete andere Struktur kann vereinfacht werden, indem die Elemente der eingebetteten Struktur direkt in der Hauptstruktur platziert werden. Alternativ kann die Struktur auch eingebettet bleiben, wie in diesem Beispiel gezeigt.  
  
-   `MyArrayStruct` enthält ein Array von ganzen Zahlen. Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut legt den <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswert auf **ByValArray** fest, womit die Anzahl der Elemente im Array angegeben wird.  
  
 Für alle Strukturen in diesem Beispiel wird das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut angewendet, um sicherzustellen, dass die Member im Speicher sequenziell in der Reihenfolge ihres Auftretens angeordnet werden.  
  
 Die `LibWrap`-Klasse enthält verwaltete Prototypen für die Methoden `TestStructInStruct`, `TestStructInStruct3` und `TestArrayInStruct`, die von der `App`-Klasse aufgerufen werden. Jeder Prototyp deklariert einen einzelnen Parameter wie folgt:  
  
-   `TestStructInStruct` deklariert einen Verweis auf den Typ `MyPerson2` als ihren Parameter.  
  
-   `TestStructInStruct3` deklariert den Typ `MyPerson3` als ihren Parameter und übergibt den Parameter als Wert.  
  
-   `TestArrayInStruct` deklariert einen Verweis auf den Typ `MyArrayStruct` als ihren Parameter.  
  
 Strukturen als Argumente von Methoden werden als Wert übergeben, es sei denn, der Parameter enthält das **Ref**-Schlüsselwort (**ByRef** in Visual Basic). Zum Beispiel übergibt die `TestStructInStruct`-Methode einen Verweis (den Wert einer Adresse) auf ein Objekt vom Typ `MyPerson2` an nicht verwalteten Code. Um die Struktur zu bearbeiten, auf die `MyPerson2` zeigt, erstellt das Beispiel einen Puffer einer angegebenen Größe und gibt dessen Adresse zurück, indem die Methoden <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> kombiniert werden. Anschließend kopiert das Beispiel den Inhalt der verwalteten Struktur in den nicht verwalteten Puffer. Zum Schluss verwendet das Beispiel die <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType>-Methode für das Marshalling von Daten aus dem nicht verwalteten Puffer in ein verwaltetes Objekt sowie die <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType>-Methode, um den nicht verwalteten Speicherblock freizugeben.  
  
### <a name="declaring-prototypes"></a>Deklarieren von Prototypen  
 [!code-cpp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
 [!code-csharp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
 [!code-vb[Conceptual.Interop.Marshaling#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]  
  
### <a name="calling-functions"></a>Aufrufen von Funktionen  
 [!code-cpp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
 [!code-csharp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
 [!code-vb[Conceptual.Interop.Marshaling#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]  
  
## <a name="findfile-sample"></a>FindFile-Beispiel  
 Dieses Beispiel demonstriert, wie eine Struktur, die eine zweite, eingebettete Struktur enthält, an eine nicht verwaltete Funktion übergeben wird. Außerdem wird veranschaulicht, wie Sie das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut verwenden, um ein Arrays mit fester Länge innerhalb der Struktur zu deklarieren. In diesem Beispiel werden die Elemente der eingebetteten Struktur der übergeordneten Struktur hinzugefügt. Ein Beispiel für eine nicht vereinfachte eingebettete Struktur finden Sie unter [Beispiel für Strukturen](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100)).  
  
 Das "FindFile"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:  
  
-   **FindFirstFile** aus „Kernel32.dll“ exportiert.  
  
    ```  
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);  
    ```  
  
 Die ursprüngliche, an die Funktion übergebene Struktur enthält die folgenden Elemente:  
  
```  
typedef struct _WIN32_FIND_DATA   
{  
  DWORD    dwFileAttributes;   
  FILETIME ftCreationTime;   
  FILETIME ftLastAccessTime;   
  FILETIME ftLastWriteTime;   
  DWORD    nFileSizeHigh;   
  DWORD    nFileSizeLow;   
  DWORD    dwReserved0;   
  DWORD    dwReserved1;   
  TCHAR    cFileName[ MAX_PATH ];   
  TCHAR    cAlternateFileName[ 14 ];   
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;  
```  
  
 In diesem Beispiel enthält die `FindData`-Klasse einen entsprechenden Datenmember für jedes Element der Originalstruktur und der eingebetteten Struktur. Anstelle zweier ursprünglicher Zeichenpuffer ersetzt die Klasse Zeichenfolgen. Das **MarshalAsAttribute**-Attribut legt die <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration auf **ByValTStr** fest. Dieser Wert wird zum Identifizieren der Inlinezeichenarrays mit fester Länge verwendet, die innerhalb der nicht verwalteten Strukturen erscheinen.  
  
 Die `LibWrap`-Klasse enthält einen verwalteten Prototyp der `FindFirstFile`-Methode, der die `FindData`-Klasse als Parameter übergibt. Der Parameter muss mit den Attributen <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> deklariert werden, weil Klassen, die Verweistypen sind, standardmäßig als In-Parameter übergeben werden.  
  
### <a name="declaring-prototypes"></a>Deklarieren von Prototypen  
 [!code-cpp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
 [!code-csharp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
 [!code-vb[Conceptual.Interop.Marshaling#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]  
  
### <a name="calling-functions"></a>Aufrufen von Funktionen  
 [!code-cpp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
 [!code-csharp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]  
  
## <a name="unions-sample"></a>Unions-Beispiel  
 Dieses Beispiel veranschaulicht, wie Strukturen, die nur Werttypen enthalten, sowie Strukturen, die einen Werttyp und eine Zeichenfolge enthalten, als Parameter an eine nicht verwaltete Funktion übergeben werden, die eine Union erwartet. Eine Union stellt einen Speicherbereich dar, der von zwei oder mehr Variablen gemeinsam genutzt werden kann.  
  
 Das "Unions"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:  
  
-   **TestUnion** aus „PinvokeLib.dll“ exportiert.  
  
    ```  
    void TestUnion(MYUNION u, int type);  
    ```  
  
 [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die eine Implementierung für die zuvor aufgelistete Funktion und zwei Unions enthält: **MYUNION** und **MYUNION2**. Die Union enthält die folgenden Elemente:  
  
```  
union MYUNION  
{  
    int number;  
    double d;  
}  
  
union MYUNION2  
{  
    int i;  
    char str[128];  
};  
```  
  
 In verwaltetem Code sind Unions als Strukturen definiert. Die `MyUnion`-Struktur enthält zwei Werttypen als Member: einen Integer- und einen Double-Wert. Das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut wird festgelegt, um die genaue Position der einzelnen Datenmember zu kontrollieren. Das <xref:System.Runtime.InteropServices.FieldOffsetAttribute>-Attribut stellt die physische Position von Feldern innerhalb der nicht verwalteten Darstellung einer Union bereit. Beachten Sie, dass beide Member denselben Offsetwert besitzen, sodass die Member denselben Speicherbereich definieren können.  
  
 `MyUnion2_1` und `MyUnion2_2` enthalten einen Werttyp (Integer) bzw. eine Zeichenfolge. In verwaltetem Code dürfen Werttypen und Verweistypen nicht überlappen. Dieses Beispiel verwendet das Überladen von Methoden, um dem Aufrufer die Verwendung beider Typen zu ermöglichen, wenn dieselbe nicht verwaltete Funktion aufgerufen wird. Das Layout von `MyUnion2_1` ist explizit und besitzt einen genauen Offsetwert. Im Gegensatz dazu verfügt `MyUnion2_2` über ein sequenzielles Layout, da explizite Layouts für Verweistypen nicht zulässig sind. Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut legt die <xref:System.Runtime.InteropServices.UnmanagedType>-Enumeration auf **ByValTStr** fest. Dieser Wert wird zum Identifizieren der Inlinezeichenarrays mit fester Länge verwendet, die innerhalb der nicht verwalteten Darstellung der Union erscheinen.  
  
 Die `LibWrap`-Klasse enthält die Prototypen für die Methoden `TestUnion` und `TestUnion2`. `TestUnion2` wird überladen, um `MyUnion2_1` oder `MyUnion2_2` als Parameter zu deklarieren.  
  
### <a name="declaring-prototypes"></a>Deklarieren von Prototypen  
 [!code-cpp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
 [!code-csharp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
 [!code-vb[Conceptual.Interop.Marshaling#28](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]  
  
### <a name="calling-functions"></a>Aufrufen von Funktionen  
 [!code-cpp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
 [!code-csharp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
 [!code-vb[Conceptual.Interop.Marshaling#29](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]  
  
## <a name="systime-sample"></a>SysTime-Beispiel  
 Dieses Beispiel demonstriert, wie ein Zeiger auf eine Klasse an eine nicht verwaltete Funktion übergeben wird, die einen Zeiger auf eine Struktur erwartet.  
  
 Das "SysTime"-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:  
  
-   **GetSystemTime** aus Kernel32.dll exportiert.  
  
    ```  
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);  
    ```  
  
 Die ursprüngliche, an die Funktion übergebene Struktur enthält die folgenden Elemente:  
  
```  
typedef struct _SYSTEMTIME {   
    WORD wYear;   
    WORD wMonth;   
    WORD wDayOfWeek;   
    WORD wDay;   
    WORD wHour;   
    WORD wMinute;   
    WORD wSecond;   
    WORD wMilliseconds;   
} SYSTEMTIME, *PSYSTEMTIME;  
```  
  
 In diesem Beispiel enthält die `SystemTime`-Klasse die Elemente der Originalstruktur, die als Klassenelemente dargestellt werden. Das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut ist so eingerichtet, dass sichergestellt wird, dass die Member im Speicher sequenziell in der Reihenfolge ihres Erscheinens angeordnet sind.  
  
 Die `LibWrap`-Klasse enthält einen verwalteten Prototyp der `GetSystemTime`-Methode, der die `SystemTime`-Klasse standardmäßig als In/Out-Parameter übergibt. Der Parameter muss mit den Attributen <xref:System.Runtime.InteropServices.InAttribute> und <xref:System.Runtime.InteropServices.OutAttribute> deklariert werden, weil Klassen, die Verweistypen sind, standardmäßig als In-Parameter übergeben werden. Damit der Aufrufer die Ergebnisse empfängt, müssen diese [direktionalen Attribute](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100)) explizit angewendet werden. Die `App`-Klasse erstellt eine neue Instanz der `SystemTime`-Klasse und greift auf deren Datenfelder zu.  
  
### <a name="code-samples"></a>Codebeispiele  
 [!code-cpp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
 [!code-csharp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
 [!code-vb[Conceptual.Interop.Marshaling#25](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]  
  
## <a name="outarrayofstructs-sample"></a>OutArrayOfStructs-Beispiel  
 Dieses Beispiel veranschaulicht, wie ein Array von Strukturen, das Integer- und String-Werte als Out-Parameter enthält, an eine nicht verwaltete Funktionen übergeben wird.  
  
 In diesem Beispiel wird veranschaulicht, wie eine systemeigene Funktion unter Verwendung der <xref:System.Runtime.InteropServices.Marshal>-Klasse und mithilfe von unsicherem Code aufgerufen wird.  
  
 Dieses Beispiel verwendet eine Wrapperfunktion und Plattformaufrufe, die in [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) definiert sind und auch in den Quelldateien bereitgestellt werden. Es verwendet die `TestOutArrayOfStructs`-Funktion und die `MYSTRSTRUCT2`-Struktur. Die Struktur enthält die folgenden Elemente:  
  
```  
typedef struct _MYSTRSTRUCT2  
{  
   char* buffer;  
   UINT size;   
} MYSTRSTRUCT2;  
```  
  
 Die `MyStruct`-Klasse enthält ein Zeichenfolgenobjekt aus ANSI-Zeichen. Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>-Feld gibt das ANSI-Format an. `MyUnsafeStruct` ist eine Struktur, die einen <xref:System.IntPtr>-Typ anstelle einer Zeichenfolge enthält.  
  
 Die `LibWrap`-Klasse enthält die überladene `TestOutArrayOfStructs`-Prototypenmethode. Wenn eine Methode einen Zeiger als Parameter deklariert, sollte die Klasse mit dem `unsafe`-Schlüsselwort markiert werden. Da [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] keinen unsicheren Code verwenden kann, sind die überladene Methode, der "unsafe"-Modifizierer und die `MyUnsafeStruct`-Struktur nicht erforderlich.  
  
 Die `App` -Klasse implementiert die `UsingMarshaling`-Methode, die alle Aufgaben durchführt, die zum Übergeben des Arrays erforderlich sind. Das Array wird mit dem `out`-Schlüsselwort (`ByRef` in Visual Basic) markiert, um anzuzeigen, dass Daten vom Aufgerufenen an den Aufrufer übergeben werden. Die Implementierung verwendet die folgenden <xref:System.Runtime.InteropServices.Marshal>-Klassenmethoden:  
  
-   <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> für das Marshalling von Daten aus dem nicht verwalteten Speicherblock zu einem verwalteten Objekt.  
  
-   <xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> zum Freigeben des für Zeichenfolgen in der Struktur reservierten Speichers.  
  
-   <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> zum Freigeben des für das Array reservierten Speichers.  
  
 Wie zuvor erwähnt, lässt C# unsicheren Code zu, und [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] nicht. In dem C#-Beispiel ist `UsingUnsafePointer` eine alternative Methodenimplementierung, die Zeiger anstelle der <xref:System.Runtime.InteropServices.Marshal>-Klasse verwendet, um das Array, das die `MyUnsafeStruct`-Struktur enthält, zurück zu übergeben.  
  
### <a name="declaring-prototypes"></a>Deklarieren von Prototypen  
 [!code-cpp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
 [!code-csharp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
 [!code-vb[Conceptual.Interop.Marshaling#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]  
  
### <a name="calling-functions"></a>Aufrufen von Funktionen  
 [!code-cpp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
 [!code-csharp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
 [!code-vb[Conceptual.Interop.Marshaling#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]  
  
## <a name="see-also"></a>Siehe auch  
 [Marshallen von Daten mit Plattformaufruf](marshaling-data-with-platform-invoke.md)  
 [Datentypen für Plattformaufruf](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))  
 [Marshallen von Zeichenfolgen](marshaling-strings.md)  
 [Marshallen von Typenarrays](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))
