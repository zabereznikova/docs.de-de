---
title: Aktivieren der Vervollständigung mit der TAB-TASTE
description: In diesem Artikel erfahren Sie, wie Sie die Vervollständigung mit der TAB-TASTE für die .NET Core-CLI für PowerShell, Bash und zsh aktivieren.
author: thraka
ms.author: adegeo
ms.date: 11/03/2019
ms.openlocfilehash: 8c5d6a254db5ba21417ba45122ed0d7cb093c7c3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739312"
---
# <a name="how-to-enable-tab-completion-for-net-core-cli"></a>Aktivieren der Vervollständigung mit der TAB-TASTE für .NET Core-CLI

Ab .NET Core 2.0 SDK unterstützt die .NET Core-CLI die Vervollständigung mit der TAB-TASTE. In diesem Artikel wird beschrieben, wie Sie die Vervollständigung mit der TAB-TASTE für drei Shells (PowerShell, Bash und zsh) konfigurieren. Möglicherweise unterstützen auch andere Shells die automatische Vervollständigung. Informationen zum Konfigurieren der automatischen Vervollständigung finden Sie in der jeweiligen Dokumentation. Die Schritte sollten den in diesem Artikel beschriebenen Schritten ähneln.

[!INCLUDE [topic-appliesto-net-core-2plus](~/includes/topic-appliesto-net-core-2plus.md)]

Nach dem Einrichten wird die Vervollständigung mit der TAB-TASTE für die .NET Core-CLI durch Eingeben eines `dotnet`-Befehls in der Shell und anschließendes Drücken der TAB-Taste ausgelöst. Die aktuelle Befehlszeile wird an den Befehl `dotnet complete` gesendet, und die Ergebnisse werden von der Shell verarbeitet. Sie können die Ergebnisse ohne Aktivierung der Vervollständigung mit der TAB-TASTE testen, indem Sie etwas direkt an den Befehl `dotnet complete` senden. Beispiel:

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

Wenn dieser Befehl nicht funktioniert, stellen Sie sicher, dass .NET Core 2.0 SDK oder höher installiert ist. Wenn es installiert ist, aber dieser Befehl trotzdem nicht funktioniert, vergewissern Sie sich, dass der `dotnet`-Befehl in eine Version von .NET Core 2.0 SDK und höher aufgelöst wird. Verwenden Sie den Befehl `dotnet --version`, um festzustellen, in welche Version von `dotnet` der aktuelle Pfad aufgelöst wird. Weitere Informationen finden Sie unter [Auswählen der zu verwendenden .NET Core-Version](../versions/selection.md).

### <a name="examples"></a>Beispiele

Nachfolgend sind einige Beispiele dafür aufgelistet, was durch die Vervollständigung mit der TAB-TASTE bereitgestellt wird:

Eingabe                                | Vervollständigung                                                                     | Grund
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | `add` ist der erste Unterbefehl in alphabetischer Reihenfolge.
`dotnet add p⇥`                      | `dotnet add --help`                                                          | Bei der Vervollständigung mit der TAB-TASTE werden Teilzeichenfolgen verglichen, und `--help` ist die erste Übereinstimmung in alphabetischer Reihenfolge.
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | Bei erneutem Drücken der TAB-TASTE wird der nächste Vorschlag angezeigt.      
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | Ergebnisse werden in alphabetischer Reihenfolge zurückgegeben.
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | Bei der Vervollständigung mit der TAB-TASTE wird die Projektdatei beachtet.

## <a name="powershell"></a>PowerShell

Wenn Sie die Vervollständigung mit der TAB-TASTE zu **PowerShell** für die .NET Core-CLI hinzufügen möchten, erstellen oder bearbeiten Sie das in der Variablen `$PROFILE` gespeicherte Profil. Weitere Informationen finden Sie unter [Erstellen Ihres Profils](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) und [Profile und Ausführungsrichtlinie](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy). 

Fügen Sie Ihrem Profil den folgenden Code hinzu:

```powershell
# PowerShell parameter completion shim for the dotnet CLI 
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a>Bash

Wenn Sie die Vervollständigung mit der TAB-TASTE der **Bash**-Shell für die .NET Core-CLI hinzufügen möchten, fügen Sie der Datei `.bashrc` den folgenden Code hinzu:

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}" 2>/dev/null)"
  if [ $? -ne 0 ]; then
    completions=""
  fi

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a>zsh

Wenn Sie die Vervollständigung mit der TAB-TASTE der **zsh**-Shell für die .NET Core-CLI hinzufügen möchten, fügen Sie der Datei `.zshrc` den folgenden Code hinzu:

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete() 
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
