---
title: -appconfig (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /appconfig
helpviewer_keywords:
- /appconfig compiler option [C#]
- -appconfig compiler option [C#]
- appconfig compiler option [C#]
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
ms.openlocfilehash: 102ed3977d56ace0dab63b1f066cc10a6fc5dfbf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514061"
---
# <a name="-appconfig-c-compiler-options"></a><span data-ttu-id="a666f-102">-appconfig (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a666f-102">-appconfig (C# Compiler Options)</span></span>
<span data-ttu-id="a666f-103">Mit der Compileroption **-appconfig** kann eine C#-Anwendung den Speicherort der Anwendungskonfigurationsdatei („app.config“) der Assembly für die Common Language Runtime (CLR) zur Assemblybindungszeit festlegen.</span><span class="sxs-lookup"><span data-stu-id="a666f-103">The **-appconfig** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a666f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a666f-104">Syntax</span></span>  
  
```console  
-appconfig:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="a666f-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="a666f-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="a666f-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a666f-106">Required.</span></span> <span data-ttu-id="a666f-107">Die Anwendungskonfigurationsdatei mit den Assemblybindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="a666f-107">The application configuration file that contains assembly binding settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a666f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a666f-108">Remarks</span></span>  
 <span data-ttu-id="a666f-109">Der Gebrauch von **-appconfig** stellt ein erweitertes Szenario dar, in dem eine Assembly gleichzeitig auf die Version von .NET Framework und von .NET Framework for Silverlight einer bestimmten Verweisassembly verweisen muss.</span><span class="sxs-lookup"><span data-stu-id="a666f-109">One use of **-appconfig** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="a666f-110">Ein in Windows Presentation Foundation (WPF) geschriebener XAML-Designer muss möglicherweise für die Benutzeroberfläche des Designers sowohl auf den WPF-Desktop als auch auf die Teilmenge von WPF, die in Silverlight enthalten ist, verweisen.</span><span class="sxs-lookup"><span data-stu-id="a666f-110">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="a666f-111">Dieselbe Designerassembly muss auf beide Assembly zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a666f-111">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="a666f-112">Standardmäßig verursachen die separaten Verweise einen Compilerfehler, da die Assemblybindung die zwei Assemblys als Entsprechung ansieht.</span><span class="sxs-lookup"><span data-stu-id="a666f-112">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span>  
  
 <span data-ttu-id="a666f-113">Mit der Compileroption **-appconfig** können Sie den Speicherort einer app.config-Datei festlegen, die das Standardverhalten wie im folgenden Beispiel dargestellt mit dem `<supportPortability>`-Tag deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a666f-113">The **-appconfig** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 <span data-ttu-id="a666f-114">Der Compiler übergibt den Speicherort der Datei an die Assemblybindungslogik der CLR.</span><span class="sxs-lookup"><span data-stu-id="a666f-114">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a666f-115">Wenn Sie die Microsoft-Build-Engine (MSBuild) verwenden, um Ihre Anwendung zu erstellen, können Sie die Compileroption **-appconfig** festlegen, indem Sie ein Eigenschaftentag in die CSPROJ-Datei einfügen.</span><span class="sxs-lookup"><span data-stu-id="a666f-115">If you are using the Microsoft Build Engine (MSBuild) to build your application, you can set the **-appconfig** compiler option by adding a property tag to the .csproj file.</span></span> <span data-ttu-id="a666f-116">Fügen Sie den Eigenschaftentag `<UseAppConfigForCompiler>` in die CSPROJ-Datei ein, und legen Sie dessen Wert auf `true` fest, um die app.config-Datei zu verwenden, die bereits im Projekt angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a666f-116">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the .csproj file and set its value to `true`.</span></span> <span data-ttu-id="a666f-117">Fügen Sie den Eigenschaftentag `<AppConfigForCompiler>` in die CSPROJ-Datei ein, und legen Sie dessen Wert auf den Speicherort der Datei fest, um eine andere app.config-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a666f-117">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a666f-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a666f-118">Example</span></span>  
 <span data-ttu-id="a666f-119">In folgendem Beispiel wird eine app.config-Datei gezeigt, die es einer Anwendung ermöglicht, über Verweise sowohl auf die .NET Framework-Implementierung als auch die .NET Framework for Silverlight-Implementierung jeder .NET Framework-Assembly zu verfügen, die in beiden Implementierungen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a666f-119">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="a666f-120">Die Compileroption **-appconfig** gibt den Speicherort der app.config-Datei an.</span><span class="sxs-lookup"><span data-stu-id="a666f-120">The **-appconfig** compiler option specifies the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
      <runtime>  
      <assemblyBinding>  
            <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
            <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
      </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a666f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a666f-121">See also</span></span>

- [<span data-ttu-id="a666f-122">\<supportPortability> Element</span><span class="sxs-lookup"><span data-stu-id="a666f-122">\<supportPortability> Element</span></span>](../../../framework/configure-apps/file-schema/runtime/supportportability-element.md)
- [<span data-ttu-id="a666f-123">C#-Compileroptionen alphabetisch sortiert</span><span class="sxs-lookup"><span data-stu-id="a666f-123">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)
