---
title: Erstellen von Schattenkopien von Assemblys
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], shadow copying
- application domains, shadow copying assemblies
- shadow copying assemblies
ms.assetid: de8b8759-fca7-4260-896b-5a4973157672
ms.openlocfilehash: 9fc8a4aeeeca40f71ed9114a9db40b9a56e5fe6b
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204573"
---
# <a name="shadow-copying-assemblies"></a>Erstellen von Schattenkopien von Assemblys

Schattenkopien sorgen dafür, dass Assemblys, die in einer Anwendungsdomäne verwendet werden, aktualisiert werden können, ohne die Anwendungsdomäne zu entladen. Dies ist besonders hilfreich für Anwendungen, die permanent verfügbar sein müssen, wie ASP.NET-Websites.

> [!IMPORTANT]
> Shadow copying is not supported in Windows 8.x Store apps.

Die Common Language Runtime sperrt eine Assemblydatei, wenn die Assembly geladen ist, daher kann die Datei erst aktualisiert werden, wenn die Assembly entladen wurde. Die einzige Möglichkeit zum Entladen einer Assembly aus einer Anwendungsdomäne besteht darin, die Anwendungsdomäne zu entladen, sodass eine Assembly unter normalen Umständen erst auf dem Datenträger aktualisiert werden kann, wenn alle Anwendungsdomänen, in der sie genutzt wird, entladen wurden.

Wenn eine Anwendungdomäne für die Erstellung von Schattenkopien von Dateien konfiguriert ist, werden Assemblys aus dem Anwendungspfad an einen anderen Speicherort kopiert und von dort aus geladen. Die Kopie wird gesperrt, aber die ursprüngliche Assemblydatei wird entsperrt und kann aktualisiert werden.

> [!IMPORTANT]
> Die einzigen Assemblys, von denen Schattenkopien erstellt werden können, sind diejenigen, die im Anwendungsverzeichnis oder dessen Unterverzeichnissen gespeichert sind, die bei der Konfiguration der Anwendungsdomäne von den Eigenschaften <xref:System.AppDomainSetup.ApplicationBase%2A> und <xref:System.AppDomainSetup.PrivateBinPath%2A> festgelegt werden. Von Assemblys, die im globalen Assemblycache gespeichert sind, werden keine Schattenkopien erstellt.

Dieser Artikel enthält folgende Abschnitte:

- [Aktivieren und Verwenden der Schattenkopiefunktion](#EnablingAndUsing) beschreibt die grundlegende Verwendung sowie die Optionen in Verbindung mit Schattenkopien.

- [Startleistung](#StartupPerformance) beschreibt die Änderungen, die an der Schattenkopiefunktion in .NET Framework 4 vorgenommen werden, um die Startleistung zu verbessern. Außerdem wird erläutert, wie das Verhalten vorheriger Versionen wiederhergestellt werden kann.

- [Veraltete Methoden](#ObsoleteMethods) beschreibt die Änderungen, die an den Eigenschaften und Methoden vorgenommen wurden, die die Schattenkopiefunktion in .NET Framework 2.0 steuern.

<a name="EnablingAndUsing"></a>

## <a name="enabling-and-using-shadow-copying"></a>Aktivieren und Verwenden der Schattenkopiefunktion

Sie können die Eigenschaften der <xref:System.AppDomainSetup>-Klasse wie folgt verwenden, um eine Anwendungsdomäne für Schattenkopien zu konfigurieren:

- Aktivieren Sie die Schattenkopiefunktion, indem Sie die <xref:System.AppDomainSetup.ShadowCopyFiles%2A>-Eigenschaft auf den Zeichenfolgenwert `"true"` festlegen.

  Standardmäßig bewirkt diese Einstellung, dass alle Assemblys im Anwendungspfad in einen Downloadcache kopiert werden, bevor sie geladen werden. Dies ist der gleiche Cache, der von der Common Language Runtime zum Speichern von Dateien verwendet wird, die von anderen Computern heruntergeladen wurden, und die Common Language Runtime löscht diese Dateien automatisch, wenn sie nicht mehr benötigt werden.

- Legen Sie optional einen benutzerdefinierten Speicherort für die Schattenkopien von Dateien fest, indem Sie die Eigenschaften <xref:System.AppDomainSetup.CachePath%2A> und <xref:System.AppDomainSetup.ApplicationName%2A> verwenden.

  Der Basispfad für den Speicherort wird gebildet, indem die Eigenschaft <xref:System.AppDomainSetup.ApplicationName%2A> mit der Eigenschaft <xref:System.AppDomainSetup.CachePath%2A> als Unterverzeichnis verkettet wird. Schattenkopien von Assemblys werden in die Unterverzeichnisse dieses Pfades gesetzt und nicht in den Basispfad selbst.

  > [!NOTE]
  > Wenn die <xref:System.AppDomainSetup.ApplicationName%2A>-Eigenschaft nicht festgelegt wird, wird die <xref:System.AppDomainSetup.CachePath%2A>-Eigenschaft ignoriert und der Downloadcache wird verwendet. Es werden keine Ausnahmen ausgelöst.

  Wenn Sie einen benutzerdefinierten Speicherort festlegen, sind Sie selbst für die Bereinigung der Verzeichnisse und das Löschen der kopierten Dateien zuständig, wenn diese nicht mehr benötigt werden. Sie werden nicht automatisch gelöscht.

  Es gibt einige Gründe, warum Sie ggf. einen benutzerdefinierten Speicherort für Schattenkopien von Dateien anlegen sollten. Möglicherweise möchten Sie einen benutzerdefinierten Speicherort für Schattenkopien von Dateien anlegen, wenn Ihre Anwendung eine große Anzahl Kopien erstellt. Der Downloadcache ist in der Größe und nicht in der Lebensdauer begrenzt, daher ist es möglich, dass die Common Language Runtime versucht, eine Datei zu löschen, die noch verwendet wird. Ein weiterer Grund für das Einrichten eines benutzerdefinierten Speicherorts ist folgender: Wenn Benutzer, die Ihre Anwendung ausführen, keinen Schreibzugriff auf den Verzeichnisspeicherort haben, den die Common Language Runtime als Downloadcache verwendet.

- Begrenzen Sie optional die Assemblys, von denen Schattenkopien erstellt werden, indem Sie die <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>-Eigenschaft verwenden.

  Wenn Sie die Schattenkopiefunktion für eine Anwendungsdomäne aktivieren, werden standardmäßig alle Assemblys im Anwendungspfad kopiert, d. h. in den Verzeichnissen, die von den Eigenschaften <xref:System.AppDomainSetup.ApplicationBase%2A> und <xref:System.AppDomainSetup.PrivateBinPath%2A> festgelegt wurden. Sie können den Kopiervorgang auf ausgewählte Verzeichnisse beschränken, indem Sie eine Zeichenfolge erstellen, der nur die Verzeichnisse enthält, in denen Schattenkopien erstellt werden sollen. Weisen Sie die Zeichenfolge dann der <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>-Eigenschaft zu. Trennen Sie die Verzeichnisse mit Semikolons. Die einzigen Assemblys, von denen Schattenkopien erstellt werden, sind nun die in den ausgewählten Verzeichnissen.

  > [!NOTE]
  > Wenn Sie der <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>-Eigenschaft keine Zeichenfolge zuweisen oder wenn Sie diese Eigenschaft nicht auf `null` festlegen, werden von allen Assemblys in den Verzeichnissen, die mit den Eigenschaften <xref:System.AppDomainSetup.ApplicationBase%2A> und <xref:System.AppDomainSetup.PrivateBinPath%2A> angegeben werden, Schattenkopien erstellt.

  > [!IMPORTANT]
  > Verzeichnispfade dürfen keine Semikolons enthalten, da das Semikolon das Trennzeichen ist. Es gibt kein Escapezeichen für Semikolons.

<a name="StartupPerformance"></a>

## <a name="startup-performance"></a>Startleistung

Wenn eine Anwendungsdomäne, in der die Schattenkopiefunktion verwendet wird, gestartet wird, kommt es zu einer Verzögerung, während die Assemblys im Anwendungsverzeichnis in das Verzeichnis für Schattenkopien kopiert oder während überprüft wird, ob sie sich bereits an diesem Speicherort befinden. Vor .NET Framework 4.0 wurden alle Assemblys in ein temporäres Verzeichnis kopiert. Jede Assembly wurde geöffnet, um den Assemblynamen zu überprüfen, und der starke Name wurde validiert. Jede Assembly wurde überprüft, um zu sehen, ob sie aktueller als die Kopie im Schattenkopieverzeichnis ist. Falls ja, wurde sie in das Schattenkopieverzeichnis kopiert. Abschließend wurden die temporären Kopien verworfen.

Ab .NET Framework 4 besteht das standardmäßige Startverhalten darin, Datum und Uhrzeit jeder Assembly im Anwendungsverzeichnis direkt mit dem Datum und der Uhrzeit der Kopie im Schattenkopieverzeichnis zu vergleichen. Wenn die Assembly aktualisiert wurde, wird sie mit der gleichen Prozedur wie in älteren Versionen von .NET Framework kopiert; andernfalls wird die Schattenkopie im Schattenkopieverzeichnis geladen.

Die sich hieraus ergebende Leistungsverbesserung ist enorm für Anwendungen, in denen Assemblys nicht häufig geändert werden und Änderungen in der Regel nur an einer kleinen Teilmenge von Assemblys vorgenommen werden. Wenn ein Großteil der Assemblys in einer Anwendung häufig geändert wird, kann das neue Standardverhalten zu einem Leistungsverlust führen. Sie können das Startverhalten vorheriger Versionen von .NET Framework wiederherstellen, indem Sie das [\<<shadowCopyVerifyByTimestamp>-Element](../configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md) mit `enabled="false"` zur Konfigurationsdatei hinzufügen.

<a name="ObsoleteMethods"></a>

## <a name="obsolete-methods"></a>Veraltete Methoden

Die <xref:System.AppDomain>-Klasse verfügt über mehrere Methoden, wie <xref:System.AppDomain.SetShadowCopyFiles%2A> und <xref:System.AppDomain.ClearShadowCopyPath%2A>, die verwendet werden können, um die Erstellung von Schattenkopien in einer Anwendungsdomäne zu steuern, diese wurde in .NET Framework 2.0 jedoch als veraltet deklariert. Die empfohlenen Methode zum Konfigurieren einer Anwendungsdomäne für die Schattenkopiefunktion besteht drin, die Eigenschaften der <xref:System.AppDomainSetup>-Klasse zu verwenden.

## <a name="see-also"></a>Siehe auch

- <xref:System.AppDomainSetup.ShadowCopyFiles%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.CachePath%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.ApplicationName%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.ShadowCopyDirectories%2A?displayProperty=nameWithType>
- [\<shadowCopyVerifyByTimestamp>-Element](../configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)
