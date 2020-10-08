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
# <a name="wfcexe-workflow-command-line-compiler-tool"></a><span data-ttu-id="b8304-103">wfc.exe (Workflow-Befehlszeilen-Compilertool)</span><span class="sxs-lookup"><span data-stu-id="b8304-103">wfc.exe (Workflow Command-line Compiler Tool)</span></span>
> [!NOTE]
> <span data-ttu-id="b8304-104">In diesem Material werden veraltete Typen und Namespaces erläutert.</span><span class="sxs-lookup"><span data-stu-id="b8304-104">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="b8304-105">Das Befehlszeilen-Compilertool wfc.exe Workflow verwendet alte Workflow Markup Dateien mit der Dateierweiterung *. xoml* (veraltet).</span><span class="sxs-lookup"><span data-stu-id="b8304-105">The wfc.exe workflow command-line compiler tool works with old workflow markup files that have the file extension *.xoml* (obsoleted).</span></span>

## <a name="compilation-process"></a><span data-ttu-id="b8304-106">Kompilierungsprozess</span><span class="sxs-lookup"><span data-stu-id="b8304-106">Compilation process</span></span>

<span data-ttu-id="b8304-107">Beim Kompilieren von Workflows werden die folgenden Prozeduren als Teil des Kompilierungsprozesses ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="b8304-107">When workflows are compiled, the following procedures are performed as part of the compilation process:</span></span>

- <span data-ttu-id="b8304-108">Die Validierung wird ausgeführt, um zu gewährleisten, dass die Workflowaktivitäten basierend auf den von den Aktivitäten für sich selbst festgelegten Regeln überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="b8304-108">Validation is performed to ensure that the workflow activities validate based on the rules that the activities have set for themselves.</span></span> <span data-ttu-id="b8304-109">Bei Validierungsfehlern wird vom Compiler eine Liste der Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b8304-109">If there are validation errors, the compiler returns a list of the errors.</span></span>  
- <span data-ttu-id="b8304-110">Eine partielle Klasse wird von der Markupdefinition generiert, die in den Compiler eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b8304-110">A partial class is generated from the markup definition that is input into the compiler.</span></span>  

- <span data-ttu-id="b8304-111">Code wird zur Unterstützung bei der Laufzeitausführung der Aktivitäten generiert.</span><span class="sxs-lookup"><span data-stu-id="b8304-111">Code is generated to help with the run-time execution of the activities.</span></span> <span data-ttu-id="b8304-112">Ereignisabonnements werden generiert, von denen Aktivitäten benachrichtigt werden, wenn die enthaltenen Aktivitäten abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="b8304-112">Event subscriptions are generated, which help activities know when the activities they contain are finished executing.</span></span>  
- <span data-ttu-id="b8304-113">Die aus der Markupdatei und der Codedatei generierten partiellen Klassen werden in den .NET Framework C#- oder Visual Basic-Compiler eingegeben.</span><span class="sxs-lookup"><span data-stu-id="b8304-113">The partial classes generated from the markup file and the partial classes from the code file are entered into the .NET Framework C# or Visual Basic compiler.</span></span> <span data-ttu-id="b8304-114">Die Ausgabe dieses Prozesses ist die .NET-Assembly, WorkflowSample.dll.</span><span class="sxs-lookup"><span data-stu-id="b8304-114">The output of this process is the .NET assembly, WorkflowSample.dll.</span></span> <span data-ttu-id="b8304-115">Sie kann zum Ausführen des Workflows bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b8304-115">This can be deployed to run the workflow.</span></span>

### <a name="compiler-options"></a><span data-ttu-id="b8304-116">Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="b8304-116">Compiler options</span></span>

<span data-ttu-id="b8304-117">In diesem Abschnitt werden die Optionen für den Befehlszeilen Compiler wfc.exe Workflow angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b8304-117">This section shows the options for the wfc.exe workflow command-line compiler.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="b8304-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b8304-118">Remarks</span></span>
> [!NOTE]
> <span data-ttu-id="b8304-119">In diesem Material werden veraltete Typen und Namespaces erläutert.</span><span class="sxs-lookup"><span data-stu-id="b8304-119">This material discusses types and namespaces that are obsolete.</span></span>

<span data-ttu-id="b8304-120">Eine Liste der autorisierten Typen wird in der Regel in der *wfc.exe.config* -Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="b8304-120">A list of authorized types is usually defined in the *wfc.exe.config* file.</span></span> <span data-ttu-id="b8304-121">Während der Überprüfungsphase der Workflow Kompilierung wird ein Workflow Quelldokument abgelehnt, wenn es oder die Datei mit den Begleit Regeln direkt auf .NET Framework Typen verweist, die nicht in einer Liste mit autorisierten Typen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b8304-121">During the validation phase of workflow compilation, a workflow source document is rejected if it or the companion rules file directly references any .NET Framework types not present in a list of authorized types.</span></span> <span data-ttu-id="b8304-122">Die Liste der autorisierten Typen ist ein XML-Dokument, in dem jeder Eintrag eine `Assembly` , einen, `Namespace` einen `TypeName` und einen autorisierten { `True`&#124;`False` }-Indikator angibt.</span><span class="sxs-lookup"><span data-stu-id="b8304-122">The list of authorized types is an XML document where each entry indicates an `Assembly`, a `Namespace`, a `TypeName`, and an Authorized {`True`&#124;`False`} indicator.</span></span> <span data-ttu-id="b8304-123">`AuthorizedType` entspricht einem Eintrag in der Liste.</span><span class="sxs-lookup"><span data-stu-id="b8304-123">`AuthorizedType` corresponds to an entry in the list.</span></span> <span data-ttu-id="b8304-124">Platzhalter Zeichen, die verwendet werden können, um komplette Namespaces einzuschließen oder auszuschließen, sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b8304-124">Wildcard character designations, which can be used to include or exclude complete namespaces, are allowed.</span></span> <span data-ttu-id="b8304-125">`Type="System.*"`Schließt z. b. alle Typen in ein <xref:System> , einschließlich Typen, die in untergeordneten Namespaces enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b8304-125">For example, `Type="System.*"` includes all types in <xref:System>, including types contained in child namespaces.</span></span>
  
<span data-ttu-id="b8304-126">Die Verwendung einer Liste der autorisierten Typen wird von der- <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> Option gesteuert `'/checktypes'` .</span><span class="sxs-lookup"><span data-stu-id="b8304-126">The use of a list of authorized types is controlled by the <xref:System.Workflow.ComponentModel.Compiler.WorkflowCompiler> option `'/checktypes'`.</span></span>

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
> <span data-ttu-id="b8304-127">Wenn `Type="System.*"` Type vorhanden ist, ist es möglich, andere unbeabsichtigte Typen, z. b `Type="System.Configuration"` ., für die Kompilierung einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="b8304-127">When `Type="System.*"` type is present, it's possible to include other unintended types, such as `Type="System.Configuration"`, for compilation.</span></span> <span data-ttu-id="b8304-128">Seien Sie vorsichtig, und überprüfen Sie jeden.</span><span class="sxs-lookup"><span data-stu-id="b8304-128">You should be cautious and review each one.</span></span> <span data-ttu-id="b8304-129">Legen Sie für jeden Typ, der eingeschränkt werden soll, `Authorized` auf fest `False` .</span><span class="sxs-lookup"><span data-stu-id="b8304-129">For any type that should be restricted, be sure to set `Authorized` to `False`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8304-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8304-130">See also</span></span>

- [<span data-ttu-id="b8304-131">Authorizedtype-Klasse</span><span class="sxs-lookup"><span data-stu-id="b8304-131">AuthorizedType class</span></span>](xref:System.Workflow.ComponentModel.Compiler.AuthorizedType)
