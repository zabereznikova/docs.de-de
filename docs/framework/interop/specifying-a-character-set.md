---
title: Angeben eines Zeichensatzes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a1b0e444ef73deac6f6e353c8e1b67d1cf361ab2
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="specifying-a-character-set"></a>Angeben eines Zeichensatzes
Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName>-Feld steuert das Marshallen von Zeichenfolgen und bestimmt, wie Plattformaufrufe Funktionsnamen in einer DLL finden. In diesem Abschnitt werden beide Verhaltensweisen beschrieben.  
  
 Einige APIs exportieren zwei Versionen von Funktionen, die Zeichenfolgenargumente verwenden: schmal (ANSI) und breit (Unicode). Die Win32-API enthält z.B. die folgenden Einstiegspunktnamen für die **MessageBox**-Funktion:  
  
-   **MessageBoxA**  
  
     Stellt einen 1-Byte-Zeichensatz im ANSI-Format zur Verfügung, der durch ein zum Namen des Einstiegspunkts hinzugefügten „A“ unterschieden wird. Aufrufe von **MessageBoxA** marshallen Zeichenfolgen immer im ANSI-Format, was auf Windows 95- und Windows 98-Plattformen üblich ist.  
  
-   **MessageBoxW**  
  
     Stellt einen 2-Byte-Zeichensatz im Unicode-Format zur Verfügung, der durch ein zum Namen des Einstiegspunkts hinzugefügten „W“ unterschieden wird. Aufrufe von **MessageBoxA** marshallen Zeichenfolgen immer im Unicode-Format, was auf Windows NT-, Windows 2000- und Windows XP-Plattformen üblich ist.  
  
## <a name="string-marshaling-and-name-matching"></a>Marshallen von Zeichenfolgen und Namensübereinstimmung  
 Das **CharSet**-Feld akzeptiert die folgenden Werte:  
  
 **CharSet.Ansi** (Standardwert)  
  
-   Marshallen von Zeichenfolgen  
  
     Plattformaufruf marshallt Zeichenfolgen aus dem verwalteten Format (Unicode) in das ANSI-Format.  
  
-   Namensübereinstimmung  
  
     Wenn das <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=fullName>-Feld **TRUE**entspricht, wie es standardmäßig in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] der Fall ist, sucht der Plattformaufruf nur nach dem von Ihnen angegebenen Namen. Wenn Sie z.B. **MessageBox** angeben, sucht der Plattformaufruf nach **MessageBox** und schlägt fehl, wenn er die exakte Schreibweise nicht finden kann.  
  
     Wenn das **ExactSpelling**-Feld **FALSE** ist, wie es standardmäßig in C++ und C# der Fall ist, sucht der Plattformaufruf zunächst nach dem zerlegten Alias (**MessageBox**), und dann nach dem ergänzten Namen (**MessageBoxA**), wenn der zerlegte Alias nicht gefunden wird. Beachten Sie, dass die Namensübereinstimmung des ANSI-Verhaltens sich von der Namensübereinstimmung des Unicode-Verhaltens unterscheidet.  
  
 **CharSet.Unicode**  
  
-   Marshallen von Zeichenfolgen  
  
     Der Plattformaufruf kopiert Zeichenfolgen aus dem verwalteten Format (Unicode) in Unicode-Format.  
  
-   Namensübereinstimmung  
  
     Wenn das Feld **ExactSpelling** **TRUE** ist, wie es standardmäßig in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] der Fall ist, sucht der Plattformaufruf nur nach dem von Ihnen angegebenen Namen. Wenn Sie z.B. **MessageBox** angeben, sucht der Plattformaufruf nach **MessageBox** und schlägt fehl, wenn er die exakte Schreibweise nicht finden kann.  
  
     Wenn das **ExactSpelling**-Feld **FALSE** ist, wie es standardmäßig in C++ und C# der Fall ist, sucht der Plattformaufruf zunächst nach dem ergänzten Namen (**MessageBoxW**), und dann nach dem zerlegten Alias (**MessageBox**), wenn der ergänzte Name nicht gefunden wird. Beachten Sie, dass das Verhalten der Namensübereinstimmung von Unicode sich vom Verhalten der Namensübereinstimmung von ANSI unterscheidet.  
  
 **CharSet.Auto**  
  
-   Der Plattformaufruf basierend auf der Zielplattform zur Laufzeit wählt zwischen ANSI- und Unicode-Formaten.  
  
## <a name="specifying-a-character-set-in-visual-basic"></a>Festlegen eines Zeichensatzes in Visual Basic  
 Das folgende Beispiel deklariert die **MessageBox**-Funktion dreimal, wobei der Zeichensatz sich jedes Mal unterschiedlich verhält. Sie können das Verhalten des Zeichensatzes in Visual Basic angeben, indem Sie die Schlüsselwörter **Ansi**, **Unicode** oder **Auto** zur Deklarationsanweisung hinzufügen.  
  
 Wenn Sie das Zeichensatzschlüsselwort weglassen, wie es in der ersten Deklarationsanweisung der Fall ist, erfolgt das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName>-Feld standardmäßig im ANSI-Zeichensatz. Die zweite und dritte Anweisung in diesem Beispiel geben einen Zeichensatz explizit mit einem Schlüsselwort an.  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="specifying-a-character-set-in-c-and-c"></a>Festlegen eines Zeichensatzes in C# und C++  
 Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName>-Feld identifiziert den zugrunde liegenden Zeichensatz als ANSI oder Unicode. Der Zeichensatz steuert, wie die Zeichenfolgenargumente an eine Methode gemarshallt werden sollen. Verwenden Sie eines der folgenden Formate, um den Zeichensatz anzugeben:  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 Im folgenden Beispiel werden drei verwaltete Definitionen der **MessageBox**-Funktion angezeigt, die einen Zeichensatz anzeigen. Durch die Auslassung wird das **CharSet**-Feld in der ersten Definition standardmäßig in ANSI-Zeichensatz verwandelt.  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Beispiele für Plattformaufrufe](../../../docs/framework/interop/platform-invoke-examples.md)   
 [Marshallen von Daten mit Plattformaufruf](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)

