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
# <a name="controlbuilderinterceptor-class"></a>Controlbuilderinterceptor-Klasse

Mit der- `ControlBuilderInterceptor` Klasse kann der Kompilierungsprozess angepasst oder gesteuert werden.

## <a name="syntax"></a>Syntax

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> Die `ControlBuilderInterceptor` -Klasse ist intern und sollte nicht direkt im Code verwendet werden.
>
> Wie im Abschnitt "Hinweise" beschrieben, kann das vorhanden sein dieses Typs überprüft werden, um zu bestimmen, ob die Unterstützung für den Interceptor Typ vorhanden ist. Microsoft unterstützt keine andere Verwendung dieser Klasse in einer Produktionsanwendung unter einem beliebigen Umstand.

## <a name="remarks"></a>Bemerkungen

In .NET Framework 2,0 und .NET Framework 3,5 wurde durch die Updates vom [August 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) die Unterstützung für die Verwendung eines Interceptor Typs zum Anpassen oder Steuern des Kompilierungs Vorgangs hinzugefügt. Sie können bestimmen, ob diese Unterstützung vorhanden ist, indem Sie verwenden, <xref:System.Type.GetType?displayProperty=nameWithType> um das vorhanden sein des Typs zu überprüfen `ControlBuilderInterceptor` , wie im folgenden Code gezeigt.

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

Wenn der Rückgabewert nicht NULL ist, ist die Interceptor Unterstützung vorhanden. Wenn der Rückgabewert ist `null` , oder wenn eine Ausnahme ausgelöst wird, wurden die Updates vom August 2020 nicht installiert, und die Interceptor Unterstützung ist nicht vorhanden.

Wenn die Interceptor Unterstützung vorhanden ist, können Sie einen Interceptor Typ schreiben und registrieren, der mit dem Kompilierungsprozess auf genau dieselbe Weise wie <xref:System.Web.Compilation.ControlBuilderInterceptor> bei späteren Versionen von .NET Framework interagiert. In .NET Framework 2,0 und .NET Framework 3,5 kann der Interceptor Typ eine beliebige Klasse sein, die die folgenden Anforderungen erfüllt:

* Verfügt über einen öffentlichen, Parameter losen Konstruktor.
* Verfügt über öffentliche, nicht statische Methoden `PreControlBuilderInit` `OnProcessGeneratedCode` mit dem Namen und, die über die gleiche Signatur und Semantik wie die <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> -Methode und die- <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> Methode verfügen, die in späteren Versionen von .NET Framework vorhanden sind.

Registrieren Sie den Interceptor Type mithilfe des `aspnet:20ControlBuilderInterceptor` Schlüssels in den ASP.net-Anwendungseinstellungen ( `<appSettings>` ). Diese Anwendungs Einstellung muss in Ihrem Computer oder in der Anwendung *web.config* Datei aufgeführt werden. Geben Sie den Interceptor Typ mit dem durch die Assembly qualifizierten Typnamen an. Im folgenden Beispiel wird gezeigt, wie ein interceptortyp mit dem Namen registriert wird `Fabrikam.Interceptor` .

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

Wenn die Interceptor Unterstützung vorhanden ist, interagiert der Kompilierungsprozess mit dem aufgelisteten Typ in der oben beschriebenen Weise. Wenn die Interceptor Unterstützung fehlt, wird die Anwendungs Einstellung ignoriert und hat keine Auswirkungen.

## <a name="requirements"></a>Requirements (Anforderungen)

**Namespace:** System. Web. Compilation

**Assembly:** System. Web (in System.Web.dll)

**.NET Framework Versionen:** 3,5, 2,0
