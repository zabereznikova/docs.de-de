---
title: Angeben eines Zeichensatzes
description: In diesem Artikel erfahren Sie, wie Sie einen Zeichensatz angeben, der Codierung im engeren (ANSI) oder weiteren (Unicode) Sinne verwendet. Alternativ können Sie eine automatische Runtimeauswahl angeben.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
ms.openlocfilehash: 789753742d8714e481f038e323407cbab0499f6c
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309793"
---
# <a name="specify-a-character-set"></a>Angeben eines Zeichensatzes

Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType>-Feld steuert das Marshallen von Zeichenfolgen und bestimmt, wie Plattformaufrufe Funktionsnamen in einer DLL finden. In diesem Abschnitt werden beide Verhaltensweisen beschrieben.  
  
 Einige APIs exportieren zwei Versionen von Funktionen, die Zeichenfolgenargumente verwenden: schmal (ANSI) und breit (Unicode). Die Windows-API enthält z.B. die folgenden Einstiegspunktnamen für die **MessageBox**-Funktion:  
  
- **MessageBoxA**  
  
     Stellt einen 1-Byte-Zeichensatz im ANSI-Format zur Verfügung, der durch ein zum Namen des Einstiegspunkts hinzugefügten „A“ unterschieden wird. Aufrufe von **MessageBoxA** marshallen Zeichenfolgen immer im ANSI-Format.  
  
- **MessageBoxW**  
  
     Stellt einen 2-Byte-Zeichensatz im Unicode-Format zur Verfügung, der durch ein zum Namen des Einstiegspunkts hinzugefügten „W“ unterschieden wird. Aufrufe von **MessageBoxW** marshallen Zeichenfolgen immer im Unicode-Format.  
  
## <a name="string-marshaling-and-name-matching"></a>Marshallen von Zeichenfolgen und Namensübereinstimmung  
 Das Feld `CharSet` akzeptiert die folgenden Werte:  
  
 <xref:System.Runtime.InteropServices.CharSet.Ansi> (Standardwert)  
  
- Marshallen von Zeichenfolgen  
  
     Plattformaufruf marshallt Zeichenfolgen aus dem verwalteten Format (Unicode) in das ANSI-Format.  
  
- Namensübereinstimmung  
  
     Wenn das <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>-Feld `true` entspricht, wie es standardmäßig in Visual Basic der Fall ist, sucht der Plattformaufruf nur nach dem von Ihnen angegebenen Namen. Wenn Sie z.B. **MessageBox** angeben, sucht der Plattformaufruf nach **MessageBox** und schlägt fehl, wenn er die exakte Schreibweise nicht finden kann.  
  
     Wenn das Feld `ExactSpelling``false` ist, wie es standardmäßig in C++ und C# der Fall ist, sucht der Plattformaufruf zunächst nach dem unbeschädigten Alias (**MessageBox**) und dann nach dem beschädigten Namen (**MessageBoxA**), wenn der unbeschädigten Alias nicht gefunden wird. Beachten Sie, dass die Namensübereinstimmung des ANSI-Verhaltens sich von der Namensübereinstimmung des Unicode-Verhaltens unterscheidet.  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
- Marshallen von Zeichenfolgen  
  
     Der Plattformaufruf kopiert Zeichenfolgen aus dem verwalteten Format (Unicode) in Unicode-Format.  
  
- Namensübereinstimmung  
  
     Wenn das `ExactSpelling`-Feld `true` entspricht, wie es standardmäßig in Visual Basic der Fall ist, sucht der Plattformaufruf nur nach dem von Ihnen angegebenen Namen. Wenn Sie z.B. **MessageBox** angeben, sucht der Plattformaufruf nach **MessageBox** und schlägt fehl, wenn er die exakte Schreibweise nicht finden kann.  
  
     Wenn das Feld `ExactSpelling``false` ist, wie es standardmäßig in C++ und C# der Fall ist, sucht der Plattformaufruf zunächst nach dem beschädigten Namen (**MessageBoxW**) und dann nach dem unbeschädigten Alias (**MessageBox**), wenn der beschädigte Alias nicht gefunden wird. Beachten Sie, dass das Verhalten der Namensübereinstimmung von Unicode sich vom Verhalten der Namensübereinstimmung von ANSI unterscheidet.  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
- Der Plattformaufruf basierend auf der Zielplattform zur Laufzeit wählt zwischen ANSI- und Unicode-Formaten.  
  
## <a name="specify-a-character-set-in-visual-basic"></a>Festlegen eines Zeichensatzes in Visual Basic

Sie können das Verhalten des Zeichensatzes in Visual Basic angeben, indem Sie die Schlüsselwörter `Ansi`, `Unicode` oder `Auto` zur Deklarationsanweisung hinzufügen. Wenn Sie das Zeichensatzschlüsselwort weglassen, wird auf das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType>-Feld standardmäßig der ANSI-Zeichensatz angewendet.

Das folgende Beispiel deklariert die **MessageBox**-Funktion dreimal, wobei der Zeichensatz sich jedes Mal unterschiedlich verhält. Die erste Anweisung lässt das Zeichensatzschlüsselwort aus, sodass ANSI standardmäßig als Zeichensatz verwendet wird. Die zweite und dritte Anweisung geben einen Zeichensatz explizit mit einem Schlüsselwort an.

```vb
Friend Class NativeMethods
    Friend Declare Function MessageBoxA Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Unicode Function MessageBoxW Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="specify-a-character-set-in-c-and-c"></a>Festlegen eines Zeichensatzes in C# und C++

Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType>-Feld identifiziert den zugrunde liegenden Zeichensatz als ANSI oder Unicode. Der Zeichensatz steuert, wie die Zeichenfolgenargumente an eine Methode gemarshallt werden sollen. Verwenden Sie eines der folgenden Formate, um den Zeichensatz anzugeben:  
  
```csharp
[DllImport("DllName", CharSet = CharSet.Ansi)]
[DllImport("DllName", CharSet = CharSet.Unicode)]
[DllImport("DllName", CharSet = CharSet.Auto)]
```
  
```cpp
[DllImport("DllName", CharSet = CharSet::Ansi)]
[DllImport("DllName", CharSet = CharSet::Unicode)]
[DllImport("DllName", CharSet = CharSet::Auto)]
```
  
 Im folgenden Beispiel werden drei verwaltete Definitionen der **MessageBox**-Funktion angezeigt, die einen Zeichensatz anzeigen. Durch die Auslassung wird das Feld `CharSet` in der ersten Definition standardmäßig in ANSI-Zeichensatz verwandelt.  
  
```csharp  
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll")]
    internal static extern int MessageBoxA(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Unicode)]
    internal static extern int MessageBoxW(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Auto)]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```  
  
```cpp
typedef void* HWND;

// Can use MessageBox or MessageBoxA.
[DllImport("user32")]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Can use MessageBox or MessageBoxW.
[DllImport("user32", CharSet = CharSet::Unicode)]
extern "C" int MessageBoxW(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Must use MessageBox.
[DllImport("user32", CharSet = CharSet::Auto)]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](creating-prototypes-in-managed-code.md)
- [Beispiele für Plattformaufrufe](platform-invoke-examples.md)
- [Marshallen von Daten mit Plattformaufruf](marshaling-data-with-platform-invoke.md)
