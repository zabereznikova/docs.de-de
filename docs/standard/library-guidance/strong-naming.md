---
title: Starke Namen und Bibliotheken für .NET
description: Best Practice-Empfehlungen für starke Benennung Bibliotheken für .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: e3f7d443eb9acc84c800ea2611b803733085391c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372805"
---
# <a name="strong-naming"></a>Starke Namen

Starke Namen verweist, auf das Signieren einer Assembly mit einem Schlüssel erzeugt eine [Assembly mit starkem Namen](../../framework/app-domains/strong-named-assemblies.md). Wenn eine Assembly mit starkem Namen handelt, erstellt eine eindeutige Identität, die basierend auf den Namen und die Assembly-Versionsnummer, und es verhindert assemblykonflikte.

Starke Namen in der Nachteil ist, dass .NET Framework unter Windows ermöglicht strict Laden von Assemblys aus, sobald eine Assembly einen starken Namen besitzt. Ein Assemblyverweis mit starkem Namen muss genau die Version, die auf die verwiesen wird von einer Assembly, die Entwickler zu zwingen [konfigurieren bindungsumleitungen](../../framework/configure-apps/redirect-assembly-versions.md) , wenn die Assembly verwenden:

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

Wenn starke Namen in .NET Entwickler der Adresssyntax, ist was sie in der Regel zu beschweren sind strenge beim Laden von Assemblys. Glücklicherweise wird dieses Problem isoliert auf .NET Framework. .NET Core, Xamarin, UWP und die meisten anderen Implementierungen von .NET keine strenge beim Laden von Assemblys und den wichtigsten Nachteil von starken Namen entfernt.

Ein wichtiger Aspekt der starke Namen ist, dass es viraler handelt: einen starken Namen Assembly können nur auf anderen starken Namens Assemblys. Wenn Ihre Bibliothek nicht sichere mit dem Namen ist, haben Sie Entwickler ausgeschlossen, die eine Anwendung oder Bibliothek, die benötigt wird, verwenden sie starke Namen erstellen.

Die Vorteile der starken Namen sind:

1. Die Assembly auf die verwiesen wird, und von anderen Assemblys mit starkem Namen verwendet werden kann.
2. Die Assembly kann in den globalen Assemblycache (GAC) gespeichert werden.
3. Die Assembly kann parallel mit anderen Versionen der Assembly geladen werden. Laden von Assemblys für Seite-an-Seite ist im Allgemeinen von Anwendungen mit Plug-in-Architekturen erforderlich.

## <a name="create-strong-named-net-libraries"></a>Erstellen Sie sichere mit dem Namen Bibliotheken für .NET

Sie sollten Ihre Open-Source-Bibliotheken .NET strong benennen. Starke Namen einer Assemblys wird sichergestellt, die meisten Personen Sie verwenden können, und nur strenge assamblys wirkt sich auf .NET Framework.

> [!NOTE]
> Diese Anleitung bezieht sich auf öffentlich verteilte Bibliotheken für .NET, wie z. B. Bibliotheken für .NET auf NuGet.org veröffentlicht. Starke Namen ist nicht von den meisten Anwendungen für .NET erforderlich und sollte nicht standardmäßig ausgeführt werden.

**✔️ GGF.** starke Benennung Ihrer Bibliothek Assemblys.

**✔️ GGF.** der Schlüssel zum starken Namen in Ihr Quellcodeverwaltungssystem einchecken.

> Ein öffentlich verfügbarer Schlüssel ermöglicht Entwicklern das Ändern und Kompilieren Ihren Quellcode der Bibliothek mit dem gleichen Schlüssel.

> [!IMPORTANT]
> Wenn eine kryptografische Identität gewünscht wird, [Authenticode](/windows-hardware/drivers/install/authenticode) und [NuGet-Paketsignierung](/nuget/create-packages/sign-a-package) werden empfohlen. Starke Namen sollten nicht für Überlegungen zur Sicherheit verwendet werden.

**✔️ GGF.** erhöht die Assemblyversion nur Hauptversion geändert, damit die Benutzer zu reduzieren, bindungsumleitungen, und wie oft sie aktualisiert werden.

> Erfahren Sie mehr über [versionsverwaltung und die Version der Assembly](./versioning.md#assembly-version).

**❌ NICHT** hinzufügen, entfernen oder ändern Sie den Schlüssel für starke benennungen.

> Ändern einer Assembly starke Benennung Schlüssel ändert sich der Identität der Assembly und unterbricht kompilierten Code, der verwendet wird. Weitere Informationen finden Sie unter [binäre wichtige Änderungen](./breaking-changes.md#binary-breaking-change).

**❌ NICHT** starken Namen haben und ohne starken Namen Versionen Ihrer Bibliothek veröffentlichen. Beispiel: `Contoso.Api` und `Contoso.Api.StrongNamed`.

> Veröffentlichen zwei Pakete Forks umfassendes für Ihre Entwickler. Wenn eine Anwendung je nach beide Pakete am Ende kann Entwickler außerdem namenstypkonflikten auftreten. Als .NET betrifft, sind sie verschiedene Typen in anderen Assemblys.

>[!div class="step-by-step"]
[Zurück](./cross-platform-targeting.md)
[Weiter](./nuget.md)
