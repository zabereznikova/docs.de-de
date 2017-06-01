---
title: "Specifying a Character Set | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "platform invoke, attribute fields"
  - "attribute fields in platform invoke, CharSet"
  - "CharSet field"
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Specifying a Character Set
Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName>\-Feld steuert das Marshalling von Zeichenfolgen und bestimmt, wie Funktionsnamen durch Plattformaufruf in einer DLL gesucht werden.  In diesem Abschnitt werden beide Verhaltensweisen beschrieben.  
  
 Einige APIs exportieren zwei Versionen von Funktionen, die Zeichenfolgenargumente verwenden: eng \(ANSI\) und weit \(Unicode\).  Die Win32\-API z. B. enthält folgende Einstiegspunktnamen für die **MessageBox**\-Funktion:  
  
-   **MessageBoxA**  
  
     Stellt eine Einzelbytezeichen\-Formatierung \(ANSI\) bereit, die durch ein an den Einstiegspunktnamen angehängtes "A" gekennzeichnet ist.  Aufrufe an **MessageBoxA** marshallen Zeichenfolgen immer im ANSI\-Format, das auf Windows 95\- und Windows 98\-Plattformen üblich ist.  
  
-   **MessageBoxW**  
  
     Stellt eine Doppelbytezeichen\-Formatierung \(Unicode\) bereit. Zur Unterscheidung ist ein "W" an den Einstiegspunktnamen angehängt.  Aufrufe an **MessageBoxW** marshallen Zeichenfolgen immer im Unicode\-Format, das auf Windows NT\-, Windows 2000\- und Windows XP\-Plattformen üblich ist.  
  
## Marshallen von Zeichenfolgen und Namensvergleich  
 Das **CharSet**\-Feld lässt folgende Werte zu:  
  
 **CharSet.Ansi** \(Standardwert\)  
  
-   Marshallen von Zeichenfolgen  
  
     Durch Plattformaufruf werden Zeichenfolgen aus dem verwalteten Format \(Unicode\) ins ANSI\-Format gemarshallt.  
  
-   Namensvergleich  
  
     Wenn das <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=fullName>\-Feld den Wert **true** aufweist, also den Standardwert in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], sucht der Plattformaufruf nur nach dem angegebenen Namen.  Wenn Sie z. B. **MessageBox** angeben, schlägt die Suche durch den Plattformaufruf fehl, wenn keine exakte Übereinstimmung mit der Schreibweise von **MessageBox** gefunden werden kann.  
  
     Wenn das **ExactSpelling**\-Feld den Wert **false** aufweist, also den Standardwert in C\+\+ und C\#, wird vom Plattformaufruf zunächst nach dem nicht zerlegten Alias \(**MessageBox**\) gesucht. Wird dieser nicht gefunden, wird anschließend nach dem zerlegten Namen \(**MessageBoxA**\) gesucht.  Beachten Sie, dass das ANSI\-Namenvergleichsverhalten nicht mit dem Unicode\-Namenvergleichsverhalten übereinstimmt.  
  
 **CharSet.Unicode**  
  
-   Marshallen von Zeichenfolgen  
  
     Durch Plattformaufruf werden Zeichenfolgen aus dem verwalteten Format \(Unicode\) ins Unicode\-Format kopiert.  
  
-   Namensvergleich  
  
     Wenn das **ExactSpelling**\-Feld den Wert **true** besitzt, also den Standardwert in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], sucht der Plattformaufruf nur nach dem angegebenen Namen.  Wenn Sie z. B. **MessageBox** angeben, schlägt die Suche durch den Plattformaufruf fehl, wenn keine exakte Übereinstimmung mit der Schreibweise von **MessageBox** gefunden werden kann.  
  
     Wenn das **ExactSpelling**\-Feld den Wert **false** aufweist, also den Standardwert in C\+\+ und C\#, wird vom Plattformaufruf zunächst nach dem zerlegten Namen \(**MessageBoxW**\) gesucht. Wird dieser nicht gefunden, wird anschließend nach dem nicht zerlegten Alias \(**MessageBox**\) gesucht.  Beachten Sie, dass das Unicode\-Namenvergleichsverhalten nicht mit dem ANSI\-Namenvergleichsverhalten übereinstimmt.  
  
 **CharSet.Auto**  
  
-   Abhängig von der Zielplattform wählt der Plattformaufruf zur Laufzeit zwischen ANSI\-Format und Unicode\-Format aus.  
  
## Festlegen eines Zeichensatzes in Visual Basic  
 Im folgenden Beispiel wird die **MessageBox**\-Funktion dreimal mit jeweils unterschiedlichem Zeichensatzverhalten deklariert.  Sie können das Zeichensatzverhalten in Visual Basic festlegen, indem Sie der Deklarationsanweisung das **Ansi**\-Schlüsselwort, das **Unicode**\-Schlüsselwort oder das **Auto**\-Schlüsselwort hinzufügen.  
  
 Wenn Sie kein Schlüsselwort für den Zeichensatz festlegen, wie dies in der ersten Deklarationsanweisung der Fall ist, wird für das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName>\-Feld standardmäßig der ANSI\-Zeichensatz verwendet.  In der zweiten und dritten Anweisung in diesem Beispiel wird mittels eines Schlüsselworts explizit ein Zeichensatz festgelegt.  
  
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
  
## Festlegen eines Zeichensatzes in C\# and C\+\+  
 Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName>\-Feld identifiziert den zugrunde liegenden Zeichensatz als ANSI oder Unicode.  Der Zeichensatz steuert, wie Zeichenfolgenargumente für die Methode gemarshallt werden sollen.  Verwenden Sie eine der folgenden Formen, um den Zeichensatz anzugeben:  
  
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
  
 Im folgenden Beispiel werden drei verwaltete Definitionen der **MessageBox**\-Funktion mit Attributen angezeigt, um den Zeichensatz anzugeben.  In der ersten Definition wird durch Auslassen des **CharSet**\-Felds standardmäßig der ANSI\-Zeichensatz übernommen.  
  
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
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Platform Invoke Examples](../../../docs/framework/interop/platform-invoke-examples.md)   
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)