---
title: Aktivieren der Vervollständigung mit der TAB-TASTE
description: In diesem Artikel erfahren Sie, wie Sie die Vervollständigung mit der TAB-TASTE für die .NET-CLI für PowerShell, Bash und zsh aktivieren.
author: adegeo
ms.author: adegeo
ms.topic: how-to
ms.date: 11/03/2019
ms.openlocfilehash: 31bf5e74644680fc30ca5b79972fbed6367363e1
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634011"
---
# <a name="how-to-enable-tab-completion-for-the-net-cli"></a>Aktivieren der Vervollständigung mit der TAB-TASTE für die .NET-CLI

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

In diesem Artikel wird beschrieben, wie Sie die Vervollständigung mit der TAB-TASTE für drei Shells (PowerShell, Bash und zsh) konfigurieren. Informationen zu anderen Shells und zum Konfigurieren der Vervollständigung mit der TAB-Taste finden Sie in den jeweiligen Dokumentationen.

Nach der Einrichtung wird die Vervollständigung mit der TAB-TASTE für die .NET-CLI durch Eingeben eines `dotnet`-Befehls in die Shell und anschließendes Drücken der TAB-Taste ausgelöst. Die aktuelle Befehlszeile wird an den Befehl `dotnet complete` gesendet, und die Ergebnisse werden von der Shell verarbeitet. Sie können die Ergebnisse ohne Aktivierung der Vervollständigung mit der TAB-TASTE testen, indem Sie etwas direkt an den Befehl `dotnet complete` senden. Zum Beispiel:

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

Wenn dieser Befehl nicht funktioniert, stellen Sie sicher, dass .NET Core 2.0 SDK oder höher installiert ist. Wenn es installiert ist, aber dieser Befehl trotzdem nicht funktioniert, vergewissern Sie sich, dass der `dotnet`-Befehl in eine Version von .NET Core 2.0 SDK und höher aufgelöst wird. Verwenden Sie den Befehl `dotnet --version`, um festzustellen, in welche Version von `dotnet` der aktuelle Pfad aufgelöst wird. Weitere Informationen finden Sie unter [Auswählen der zu verwendenden .NET-Version](../versions/selection.md).

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

Wenn Sie die Vervollständigung mit der TAB-TASTE für die .NET-CLI zu **PowerShell** hinzufügen möchten, erstellen oder bearbeiten Sie das in der Variablen `$PROFILE` gespeicherte Profil. Weitere Informationen finden Sie unter [Erstellen Ihres Profils](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) und [Profile und Ausführungsrichtlinie](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).

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

Wenn Sie die Vervollständigung mit der TAB-TASTE für die .NET-CLI zur **Bash**-Shell hinzufügen möchten, fügen Sie der Datei `.bashrc` den folgenden Code hinzu:

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

Wenn Sie die Vervollständigung mit der TAB-TASTE für die .NET-CLI zur **zsh**-Shell hinzufügen möchten, fügen Sie der Datei `.zshrc` den folgenden Code hinzu:

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
