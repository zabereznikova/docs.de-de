---
title: Starke Namen und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden für starke Namen für .NET-Bibliotheken.
ms.date: 10/16/2018
ms.openlocfilehash: db268093b07a2ece7cdb8329fd789b52da9c5c32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744531"
---
# <a name="strong-naming"></a>Starke Namen

Starke Namen bezieht sich auf das Signieren einer Assembly mit einem Schlüssel, wodurch eine [Assembly mit starkem Namen](../assembly/strong-named.md) entsteht. Wenn eine Assembly einen starken Namen hat, erzeugt sie eine eindeutige Identität basierend auf dem Namen und der Versionsnummer der Assembly, und dies kann helfen, Konflikte in der Assembly zu vermeiden.

Der Nachteil eines starken Namens ist, dass das .NET Framework unter Windows ein striktes Laden von Assemblys ermöglicht, sobald eine Assembly einen starken Namen hat. Eine Referenz auf eine Assembly mit starkem Namen muss genau der Version entsprechen, auf die eine Assembly verweist. Dadurch sind Entwickler gezwungen, [Bindungsumleitungen](../../framework/configure-apps/redirect-assembly-versions.md) zu konfigurieren, wenn sie die Assembly verwenden:

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly" publicKeyToken="32ab4ba45e0a69a1" culture="neutral" />
            <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

Wenn sich .NET-Entwickler über starke Namen beschweren, geht es in der Regel um das strikte Laden einer Assembly. Dieses Problem wurde im .NET Framework isoliert. .NET Core, Xamarin, UWP und die meisten anderen .NET-Implementierungen haben kein striktes Laden von Assemblys und weisen so den wesentlichen Nachteil eines starken Namens nicht auf.

Ein wichtiger Aspekt eines starken Namens ist, dass sie viral ist: eine Assembly mit einem starken Namen kann nur auf andere Assemblys mit einem starken Namen verweisen. Wenn Ihre Bibliothek keinen starken Namen hat, dann haben Sie Entwickler, die eine Anwendung oder Bibliothek erstellen, die einen starken Namen benötigt, von der Verwendung ausgeschlossen.

Die Vorteile der starken Namen sind:

1. Die Assembly kann nur von anderen Assemblys mit starkem Namen referenziert und verwendet werden.
2. Die Assembly kann im globalen Assemblycache (GAC) gespeichert werden.
3. Die Assembly kann parallel mit anderen Versionen der Assembly geladen werden. Das parallele Laden von Assemblys ist häufig für Anwendungen mit Plug-in-Architekturen erforderlich.

## <a name="create-strong-named-net-libraries"></a>Erstellen von .NET-Bibliotheken mit starkem Namen

Sie sollten Ihren .NET-Open-Source-Bibliotheken einen starken Namen geben. Der starke Name einer Assembly stellt sicher, dass die meisten Benutzer sie verwenden können, und das strikte Laden der Assembly betrifft nur das .NET Framework.

> [!NOTE]
> Diese Anleitung bezieht sich auf öffentlich verteilte .NET-Bibliotheken, wie z.B. auf NuGet.org veröffentlichte .NET-Bibliotheken. Ein starker Namen ist für die meisten .NET-Anwendungen nicht erforderlich und sollte nicht standardmäßig vorgenommen werden.

✔️ Erwägen Sie, Ihren Bibliotheksassemblys einen starken Namen zu geben.

✔️ Erwägen Sie, den Schlüssel für die eindeutige Benennung zu Ihrem Quellcodeverwaltungssystem hinzuzufügen.

> Ein öffentlich verfügbarer Schlüssel ermöglicht es Entwicklern, den Quellcode Ihrer Bibliothek mit demselben Schlüssel zu ändern und neu zu kompilieren.
>
> Sie sollten den starken Namensschlüssel nicht öffentlich machen, wenn er in der Vergangenheit zur Vergabe von Sonderrechten in [teilweise vertrauenswürdigen Szenarien](../../framework/misc/using-libraries-from-partially-trusted-code.md) verwendet wurde. Andernfalls können Sie vorhandene Umgebungen beeinträchtigen.

> [!IMPORTANT]
> Wenn die Identität des Herausgebers des Codes erwünscht ist, werden [Authenticode](/windows-hardware/drivers/install/authenticode) und [NuGet-Paketsignierung](/nuget/create-packages/sign-a-package) empfohlen. Die Codezugriffssicherheit (Code Access Security, CAS) sollte nicht zur Risikominderung verwendet werden.

✔️ Erwägen Sie, die Assemblyversion nur bei größeren Versionsänderungen zu erhöhen, um Benutzern zu helfen, Bindungsumleitungen und die Häufigkeit ihrer Aktualisierung zu reduzieren.

> Erfahren Sie mehr über die [Versionsverwaltung und die Assemblyversion](./versioning.md#assembly-version).

❌ Den Schlüssel für die eindeutige Benennung weder hinzufügen, noch ändern oder entfernen

> Das Ändern des starken Namensschlüssels einer Assembly ändert die Identität der Assembly und zerlegt kompilierten Code, der ihn verwendet. Weitere Informationen finden Sie unter [Binäre Breaking Changes](./breaking-changes.md#binary-breaking-change).

❌ Veröffentlichen Sie NICHT die Versionen Ihrer Bibliothek mit oder ohne starkem Namen. Beispiel: `Contoso.Api` und `Contoso.Api.StrongNamed`.

> Die Veröffentlichung von zwei Paketen verzweigt Ihr Entwicklerökosystem. Auch wenn eine Anwendung letztendlich von beiden Paketen abhängig ist, kann es bei dem Entwickler zu Typnamenskonflikten kommen. Was .NET betrifft, so sind sie verschiedene Typen in verschiedenen Assemblys.

>[!div class="step-by-step"]
>[Zurück](cross-platform-targeting.md)
>[Weiter](nuget.md)
