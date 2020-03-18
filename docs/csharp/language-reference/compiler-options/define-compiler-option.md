---
title: -define (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
ms.openlocfilehash: 4a3622b6acc8ebe9c590b01b67074ae59396fc34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173743"
---
# <a name="-define-c-compiler-options"></a>-define (C#-Compileroptionen)
Die Option **-define** definiert `name` als Symbol in allen Quellcodedateien Ihres Programms.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-define:name[;name2]  
```  
  
## <a name="arguments"></a>Argumente  
 `name`, `name2`  
 Der Name eines oder mehrerer Symbole, die Sie definieren möchten.  
  
## <a name="remarks"></a>Hinweise  
 Die Option **-define** hat dieselbe Auswirkung wie die Verwendung einer [#define](../preprocessor-directives/preprocessor-define.md)-Präprozessoranweisung, außer dass die Compileroption für alle Dateien im Projekt gültig ist. Ein Symbol bleibt in einer Quelldatei definiert, bis eine [#undef](../preprocessor-directives/preprocessor-undef.md)-Anweisung in der Quelldatei die Definition entfernt. Wenn Sie die Option „-define“ verwenden, hat eine `#undef`-Anweisung in einer Datei keinerlei Auswirkung auf andere Quellcodedateien im Projekt.  
  
 Sie können die durch diese Option erstellten Symbole in Verbindung mit [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md), und [#endif](../preprocessor-directives/preprocessor-endif.md) verwenden, um Quelldateien bedingt zu kompilieren.  
  
 **-d** ist die Kurzform von **-define**.  
  
 Sie können mehrere Symbole mit **-define** definieren, indem Sie die Symbolnamen jeweils durch ein Semikolon oder Komma voneinander trennen. Beispiel:  
  
```console  
-define:DEBUG;TUESDAY  
```  
  
 Der C#-Compiler selbst definiert keine Symbole oder Makros, die Sie in Ihrem Quellcode verwenden können. Alle Symboldefinitionen müssen benutzerdefiniert sein.  
  
> [!NOTE]
> Anders als in Programmiersprachen wie C++ ist es in C# bei Verwendung von `#define` nicht zulässig, einem Symbol einen Wert zuzuweisen. Beispielsweise kann `#define` nicht zum Erstellen eines Makros oder zum Definieren einer Konstante verwendet werden. Falls Sie eine Konstante definieren müssen, verwenden Sie eine `enum`-Variable. Wenn Sie ein C++-übliches Makro erstellen möchten, erwägen Sie Alternativen wie Generics. Da Makros sehr fehleranfällig sind, ist ihre Verwendung in C# nicht zugelassen. Es stehen jedoch sicherere Alternativen zur Verfügung.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Geben Sie auf der Registerkarte **Erstellen** im Feld **Symbole für bedingte Kompilierung** das zu definierende Symbol ein. Wenn Sie z.B. das folgende Codebeispiel verwenden, geben Sie im Textfeld einfach `xx` ein.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
// preprocessor_define.cs  
// compile with: -define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test
{  
    public static void Main()
    {  
        #if (xx)
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
