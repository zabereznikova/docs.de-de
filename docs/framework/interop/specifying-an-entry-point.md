---
title: Angeben eines Einstiegspunktes
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
ms.openlocfilehash: a55e460f565c33731c5b0b29ab42b8263d3690e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125159"
---
# <a name="specifying-an-entry-point"></a>Angeben eines Einstiegspunktes

Ein Einstiegspunkt identifiziert die Position einer Funktion in einer DLL. In einem verwalteten Projekt wird diese Funktion vom ursprünglichen Namen oder vom Ordinaleinstiegspunkt einer Zielfunktion über die Grenzen der Interoperation hinaus identifiziert. Außerdem können Sie dem Einstiegspunkt einen anderen Namen zuordnen und damit die Funktion umbenennen.  
  
 Im folgenden finden Sie eine Liste möglicher Gründe für das Umbenennen einer DLL-Funktion:  
  
- Um keine API-Funktionsnamen zu verwenden, die zwischen Groß- und Kleinschreibung unterscheiden.  
  
- Um die Konventionen vorhandener Namensstandards einzuhalten.  
  
- Um Funktionen aufzunehmen, die verschiedene Datentypen verwenden (indem mehrere Versionen derselben DLL-Funktion deklariert werden).  
  
- Um die Verwendung von APIs zu vereinfachen, die ANSI- und Unicode-Versionen enthalten.  
  
 In diesem Abschnitt wird das Umbenennen einer DLL-Funktion in verwaltetem Code veranschaulicht.  
  
## <a name="renaming-a-function-in-visual-basic"></a>Umbenennen einer Funktion in Visual Basic  
 
Visual Basic verwendet das **Function**-Schlüsselwort in der **Declare**-Anweisung, um das<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>-Feld festzulegen. Das folgende Beispiel zeigt eine Basisdeklaration.  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
Sie können den **MessageBox**-Einstiegspunkt durch **MsgBox** ersetzen, indem Sie das **Alias**-Schlüsselwort wie im folgenden Beispiel dargestellt in die Definition aufnehmen. In beiden Beispielen erübrigt sich aufgrund des **Auto**-Schlüsselwortes die Angabe der Zeichensatzversion des Einstiegspunktes. Weitere Informationen zum Auswählen eines Zeichensatzes finden Sie unter [Angeben eines Zeichensatzes](specifying-a-character-set.md).  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MsgBox _
        Lib "user32.dll" Alias "MessageBox" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="renaming-a-function-in-c-and-c"></a>Umbenennen einer Funktion in C# und C++  
 Sie können das <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>-Feld verwenden, um eine DLL-Funktion nach Name oder Ordinalzahl anzugeben. Wenn der Name der Funktion in der Methodendefinition mit dem Einstiegspunkt in der DLL übereinstimmt, müssen Sie die Funktion nicht explizit mit dem **EntryPoint**-Feld identifizieren. Andernfalls verwenden Sie eine der folgenden Attributformen zur Angabe eines Namens oder einer Ordinalzahl:  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 Hinweis: Für eine Ordinalzahl müssen Sie das Pfundzeichen (#) als Präfix verwenden.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie im Code **MessageBoxA** mit **MsgBox** ersetzen, indem Sie das **EntryPoint**-Feld verwenden.  
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll", EntryPoint = "MessageBoxA")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

typedef void* HWND;
[DllImport("user32", EntryPoint = "MessageBoxA")]
extern "C" int MsgBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Erstellen von Prototypen in verwaltetem Code](creating-prototypes-in-managed-code.md)
- [Beispiele für Plattformaufrufe](platform-invoke-examples.md)
- [Marshallen von Daten mit Plattformaufruf](marshaling-data-with-platform-invoke.md)
