---
title: Controlbuilderinterceptor-Klasse
ms.date: 08/11/2020
api_name:
- System.Web.Compilation.ControlBuilderInterceptor
api_location:
- System.Web.dll
api_type:
- Assembly
topic_type:
- apiref
ms.openlocfilehash: 312d977f832d262b1bebc6638280b67b133babdf
ms.sourcegitcommit: 70d6a7e4f7187cbfa332f0f8be76566f7828cfcd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88084406"
---
# <a name="controlbuilderinterceptor-class"></a><span data-ttu-id="69142-102">Controlbuilderinterceptor-Klasse</span><span class="sxs-lookup"><span data-stu-id="69142-102">ControlBuilderInterceptor class</span></span>

<span data-ttu-id="69142-103">Mit der- `ControlBuilderInterceptor` Klasse kann der Kompilierungsprozess angepasst oder gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="69142-103">The `ControlBuilderInterceptor` class allows the compilation process to be customized or controlled.</span></span>

## <a name="syntax"></a><span data-ttu-id="69142-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69142-104">Syntax</span></span>

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> <span data-ttu-id="69142-105">Die `ControlBuilderInterceptor` -Klasse ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69142-105">The `ControlBuilderInterceptor` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="69142-106">Wie im Abschnitt "Hinweise" beschrieben, kann das vorhanden sein dieses Typs überprüft werden, um zu bestimmen, ob die Unterstützung für den Interceptor Typ vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="69142-106">As described in the Remarks section, the existence of this type can be checked to determine whether interceptor type support is present.</span></span> <span data-ttu-id="69142-107">Microsoft unterstützt keine andere Verwendung dieser Klasse in einer Produktionsanwendung unter einem beliebigen Umstand.</span><span class="sxs-lookup"><span data-stu-id="69142-107">Microsoft does not support any other use of this class in a production application under any circumstance.</span></span>

## <a name="remarks"></a><span data-ttu-id="69142-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="69142-108">Remarks</span></span>

<span data-ttu-id="69142-109">In .NET Framework 2,0 und .NET Framework 3,5 wurde durch die Updates vom [August 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) die Unterstützung für die Verwendung eines Interceptor Typs zum Anpassen oder Steuern des Kompilierungs Vorgangs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="69142-109">In .NET Framework 2.0 and .NET Framework 3.5, the [August 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) updates added support for using an interceptor type to customize or control the compilation process.</span></span> <span data-ttu-id="69142-110">Sie können bestimmen, ob diese Unterstützung vorhanden ist, indem Sie verwenden, <xref:System.Type.GetType?displayProperty=nameWithType> um das vorhanden sein des Typs zu überprüfen `ControlBuilderInterceptor` , wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="69142-110">You can determine whether this support is present by using <xref:System.Type.GetType?displayProperty=nameWithType> to check the existence of the `ControlBuilderInterceptor` type, as demonstrated in the following code.</span></span>

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

<span data-ttu-id="69142-111">Wenn der Rückgabewert nicht NULL ist, ist die Interceptor Unterstützung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="69142-111">If the return value is non-null, then interceptor support is present.</span></span> <span data-ttu-id="69142-112">Wenn der Rückgabewert ist `null` , oder wenn eine Ausnahme ausgelöst wird, wurden die Updates vom August 2020 nicht installiert, und die Interceptor Unterstützung ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="69142-112">If the return value is `null`, or if an exception is thrown, then the August 2020 updates have not been installed, and interceptor support is absent.</span></span>

<span data-ttu-id="69142-113">Wenn die Interceptor Unterstützung vorhanden ist, können Sie einen Interceptor Typ schreiben und registrieren, der mit dem Kompilierungsprozess auf genau dieselbe Weise wie <xref:System.Web.Compilation.ControlBuilderInterceptor> bei späteren Versionen von .NET Framework interagiert.</span><span class="sxs-lookup"><span data-stu-id="69142-113">If interceptor support is present, you can write and register an interceptor type that will interact with the compilation process in exactly the same way that <xref:System.Web.Compilation.ControlBuilderInterceptor> does on later versions of .NET Framework.</span></span> <span data-ttu-id="69142-114">In .NET Framework 2,0 und .NET Framework 3,5 kann der Interceptor Typ eine beliebige Klasse sein, die die folgenden Anforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="69142-114">In .NET Framework 2.0 and .NET Framework 3.5, the interceptor type can be any class that meets the following requirements:</span></span>

* <span data-ttu-id="69142-115">Verfügt über einen öffentlichen, Parameter losen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="69142-115">Has a public, parameterless constructor.</span></span>
* <span data-ttu-id="69142-116">Verfügt über öffentliche, nicht statische Methoden `PreControlBuilderInit` `OnProcessGeneratedCode` mit dem Namen und, die über die gleiche Signatur und Semantik wie die <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> -Methode und die- <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> Methode verfügen, die in späteren Versionen von .NET Framework vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="69142-116">Has public, non-static methods named `PreControlBuilderInit` and `OnProcessGeneratedCode` that have the same signature and semantics as the <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> and <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> methods, which exist in later versions of .NET Framework.</span></span>

<span data-ttu-id="69142-117">Registrieren Sie den Interceptor Type mithilfe des `aspnet:20ControlBuilderInterceptor` Schlüssels in den ASP.net-Anwendungseinstellungen ( `<appSettings>` ).</span><span class="sxs-lookup"><span data-stu-id="69142-117">Register the interceptor type by using the `aspnet:20ControlBuilderInterceptor` key in ASP.NET application settings (`<appSettings>`).</span></span> <span data-ttu-id="69142-118">Diese Anwendungs Einstellung muss in Ihrem Computer oder in der Anwendung *web.config* Datei aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="69142-118">This application setting must be listed in your computer or application *web.config* file.</span></span> <span data-ttu-id="69142-119">Geben Sie den Interceptor Typ mit dem durch die Assembly qualifizierten Typnamen an.</span><span class="sxs-lookup"><span data-stu-id="69142-119">Specify the interceptor type by using its assembly-qualified type name.</span></span> <span data-ttu-id="69142-120">Im folgenden Beispiel wird gezeigt, wie ein interceptortyp mit dem Namen registriert wird `Fabrikam.Interceptor` .</span><span class="sxs-lookup"><span data-stu-id="69142-120">The following example shows how to register an interceptor type named `Fabrikam.Interceptor`.</span></span>

```xml
<configuration>
  ...
  <appSettings>
    ...
    <add key="aspnet:20ControlBuilderInterceptor"
         value="Fabrikam.Interceptor, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
  </appSettings>
</configuration>

To retrieve the assembly-qualified name of a type, use the <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> property, as demonstrated in the following code.

```csharp
string assemblyQualifiedName = typeof(Fabrikam.Interceptor).AssemblyQualifiedName;
```

<span data-ttu-id="69142-121">Wenn die Interceptor Unterstützung vorhanden ist, interagiert der Kompilierungsprozess mit dem aufgelisteten Typ in der oben beschriebenen Weise.</span><span class="sxs-lookup"><span data-stu-id="69142-121">When interceptor support is present, the compilation process interacts with the listed type in the manner described above.</span></span> <span data-ttu-id="69142-122">Wenn die Interceptor Unterstützung fehlt, wird die Anwendungs Einstellung ignoriert und hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="69142-122">When interceptor support is absent, the application setting is ignored and has no effect.</span></span>

## <a name="requirements"></a><span data-ttu-id="69142-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="69142-123">Requirements</span></span>

<span data-ttu-id="69142-124">**Namespace:** System. Web. Compilation</span><span class="sxs-lookup"><span data-stu-id="69142-124">**Namespace:** System.Web.Compilation</span></span>

<span data-ttu-id="69142-125">**Assembly:** System. Web (in System.Web.dll)</span><span class="sxs-lookup"><span data-stu-id="69142-125">**Assembly:** System.Web (in System.Web.dll)</span></span>

<span data-ttu-id="69142-126">**.NET Framework Versionen:** 3,5, 2,0</span><span class="sxs-lookup"><span data-stu-id="69142-126">**.NET Framework versions:** 3.5, 2.0</span></span>
