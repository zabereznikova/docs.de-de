---
title: Wfc.exe (Workflow-Befehlszeilen-Compilertool)
description: Verstehen Sie wfc.exe, dem Workflow Befehlszeilen-Compilertool.
ms.date: 10/10/2020
helpviewer_keywords:
- wfc [Workflow]
- compiler tool
- wfc.exe
- Workflow, compilation
- Workflow, XOML files
- Workflow, wcf
ms.openlocfilehash: cf89962014584adf098118044b063b38b29160b7
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844612"
---
# <a name="wfcexe-workflow-command-line-compiler-tool"></a>wfc.exe (Workflow-Befehlszeilen-Compilertool)
> [!NOTE]
> In diesem Material werden veraltete Typen und Namespaces erläutert.

Das Befehlszeilen-Compilertool wfc.exe Workflow verwendet alte Workflow Markup Dateien mit der Dateierweiterung *. xoml* (veraltet).

## <a name="compilation-process"></a>Kompilierungsprozess

Beim Kompilieren von Workflows werden die folgenden Prozeduren als Teil des Kompilierungsprozesses ausgeführt:

- Die Validierung wird ausgeführt, um zu gewährleisten, dass die Workflowaktivitäten basierend auf den von den Aktivitäten für sich selbst festgelegten Regeln überprüft werden. Bei Validierungsfehlern wird vom Compiler eine Liste der Fehler zurückgegeben.  
- Eine partielle Klasse wird von der Markupdefinition generiert, die in den Compiler eingegeben wird.  

- Code wird zur Unterstützung bei der Laufzeitausführung der Aktivitäten generiert. Ereignisabonnements werden generiert, von denen Aktivitäten benachrichtigt werden, wenn die enthaltenen Aktivitäten abgeschlossen sind.  
- Die aus der Markupdatei und der Codedatei generierten partiellen Klassen werden in den .NET Framework C#- oder Visual Basic-Compiler eingegeben. Die Ausgabe dieses Prozesses ist die .NET-Assembly, WorkflowSample.dll. Sie kann zum Ausführen des Workflows bereitgestellt werden.

### <a name="compiler-options"></a>Compileroptionen

In diesem Abschnitt werden die Optionen für den Befehlszeilen Compiler wfc.exe Workflow angezeigt.

```output
    Microsoft (R) Windows Workflow Compiler version 3.0.0.0
    Copyright (C) Microsoft Corporation 2005. All rights reserved.

                      Windows Workflow Compiler Options

    wfc.exe <Xoml file list> /target:assembly [<vb/cs file list>] [/language:...]
            [/out:...] [/reference:...] [/library:...] [/debug...] [/nocode...]
             [/checktypes...] [/resource:<resource info>]

                            - OUTPUT FILE -
    /out:<file>             Output file name
    /target:assembly        Build a Windows Workflow assembly (default).
                            Short form: /t:assembly
    /target:exe             Build a Windows Workflow application.
                            Short form: /t:exe
    /delaysign[+|-]         Delay-sign the assembly using only the public portion
                            of the strong name key.
    /keyfile:<file>         Specifies a strong name key file.
    /keycontainer:<string>  Specifies a strong name key container.

                            - INPUT FILES -
    <Xoml file list>        Xoml source file name(s).
    <vb/cs file list>       Code-beside file name(s).
    /reference:<file list>  Reference metadata from the specified assembly file(s).
                            Short form is '/r:'.
    /library:<path list>    Set of directories where to lookup for the references.
                            Short form is '/lib:'.
    /resource:<resinfo>     Embed the specified resource. Short form is '/res:'.
                            resinfo format is <file>[,<name>[,public|private]].

    Rules and freeform layout files must be embedded as assembly resources.
    The resource name is constructed by using the namespace and type name
    of the activity. For example, an activity named "MyActivity" in namespace
    "WFProject" would require resource names "WFProject.MyActivity.rules"
    and/or "WFProject.MyActivity.layout".

                            - CODE GENERATION -
    /debug[+|-]             Emit full debugging information. The default is '+'.
    /nocode[+|-]            Disallow code-beside model.
                            The default is '-'. Short form is '/nc:'.
    /checktypes[+|-]        Check for permitted types in wfc.exe.config file.
                            The default is '-'. Short form is '/ct:'.

                            - LANGUAGE -
    /language:[cs|vb]       The language to use for the generated class.
                            The default is 'CS' (C#). Short form is '/l:'.
    /rootnamespace:<string> Specifies the root Namespace for all type declarations.
                            Valid only for 'VB' (Visual Basic) language.
                            Short form is '/rns:'.

                            - MISCELLANEOUS -
    /help                   Display this usage message. Short form is '/?'.
    /nologo                 Suppress compiler copyright message. Short form is '/n'.

    /nowarn                 Ignore compiler warnings. Short form is '/w'.
```

## <a name="remarks"></a>Bemerkungen
> [!NOTE]
> In diesem Material werden veraltete Typen und Namespaces erläutert.

Eine Liste der autorisierten Typen wird in der Regel in der *wfc.exe.config* -Datei definiert. Während der Überprüfungsphase der Workflow Kompilierung wird ein Workflow Quelldokument abgelehnt, wenn es oder die Datei mit den Begleit Regeln direkt auf .NET Framework Typen verweist, die nicht in einer Liste mit autorisierten Typen vorhanden sind. Die Liste der autorisierten Typen ist ein XML-Dokument, in dem jeder Eintrag eine `Assembly` , einen, `Namespace` einen `TypeName` und einen autorisierten { `True`&#124;`False` }-Indikator angibt. `AuthorizedType` entspricht einem Eintrag in der Liste. Platzhalter Zeichen, die verwendet werden können, um komplette Namespaces einzuschließen oder auszuschließen, sind zulässig. `Type="System.*"`Schließt z. b. alle Typen in ein <xref:System> , einschließlich Typen, die in untergeordneten Namespaces enthalten sind.
  
Die Verwendung einer Liste der autorisierten Typen wird von der- <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> Option gesteuert `'/checktypes'` .

```xml  
<configuration>  
  <System.Workflow.ComponentModel.WorkflowCompiler>
    <authorizedTypes>
      <targetFx version="v4.0">
        ...
        <authorizedType Assembly="System, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" Namespace="System*" TypeName="*" Authorized="True"/>
        ...
      </targetFx>
    </authorizedTypes>
  </System.Workflow.ComponentModel.WorkflowCompiler>  
</configuration>  
```

> [!WARNING]
> Wenn `Type="System.*"` Type vorhanden ist, ist es möglich, andere unbeabsichtigte Typen, z. b `Type="System.Configuration"` ., für die Kompilierung einzubeziehen. Seien Sie vorsichtig, und überprüfen Sie jeden. Legen Sie für jeden Typ, der eingeschränkt werden soll, `Authorized` auf fest `False` .

## <a name="see-also"></a>Weitere Informationen

- [Authorizedtype-Klasse](xref:System.Workflow.ComponentModel.Compiler.AuthorizedType)
