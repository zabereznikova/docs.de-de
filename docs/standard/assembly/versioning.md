---
title: Versionsverwaltung für Assemblys
ms.date: 08/20/2019
helpviewer_keywords:
- informational versions
- version numbers, assemblies
- assemblies [.NET Framework], versioning
- resolving assembly binding requests
- versioning, assemblies
ms.assetid: 775ad4fb-914f-453c-98ef-ce1089b6f903
ms.openlocfilehash: bbb3dae2ce66c93d05a2a1c0f7e426901fa7b2e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73140182"
---
# <a name="assembly-versioning"></a>Versionsverwaltung für Assemblys

Jede Version einer Assembly, die die Common Language Runtime verwendet, wird auf Assemblyebene erstellt. Die spezifische Version einer Assembly sowie die Versionen der abhängigen Assemblys sind im Assemblymanifest aufgezeichnet. Der Standardversionsrichtlinie für die Laufzeit zufolge werden Anwendungen nur in der Version ausgeführt, in der sie erstellt und getestet wurden, sofern dies nicht durch eine explizite Versionsrichtlinie in den Konfigurationsdateien (die Anwendungskonfigurationsdatei, die Herausgeberrichtliniendatei und die Administratorkonfigurationsdatei für den Computer) überschrieben wird.  
  
> [!NOTE]
> Versionen werden nur bei Assemblys mit starken Namen erstellt.  
  
Zur Auflösung einer Assemblybindungsanforderung werden von der Laufzeit mehrere Schritte ausgeführt:  
  
1. Überprüft den ursprünglichen Assemblyverweis, um zu bestimmen, welche Version der Assembly gebunden werden soll.  
  
2. Überprüft alle anwendbaren Konfigurationsdateien, um die Versionsrichtlinie anzuwenden.  
  
3. Ermittelt die richtige Assembly aus dem ursprünglichen Assemblyverweis und allen Umleitungen, die in den Konfigurationsdateien angegeben sind, und bestimmt die Version, die an die aufrufende Assembly gebunden werden soll.  
  
4. Überprüft den globalen Assemblycache, jede in den Konfigurationsdateien angegebene Codebasis und danach das Anwendungsverzeichnis und die Unterverzeichnisse anhand der Überprüfungsregeln, die in [So sucht die Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md) erklärt werden.  
  
Diese Schritte sind in der folgenden Abbildung dargestellt:  
  
![Diagramm mit den Schritten zur Auflösung einer Assemblybindungsanforderung](./media/versioning/resolve-assembly-binding-request.gif)
  
Weitere Informationen zum Konfigurieren von Anwendungen finden Sie unter [Konfigurieren von Apps](../../framework/configure-apps/index.md). Weitere Informationen zu Bindungsrichtlinien finden Sie unter [So sucht die Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md).  
  
## <a name="version-information"></a>Versionsinformationen  

Jede Assembly besitzt zwei unterschiedliche Methoden zur Darstellung der Versionsinformationen:  
  
- Die Versionsnummer der Assembly, die zusammen mit dem Assemblynamen und den Kulturinformationen zur Identität der Assembly gehört. Diese Nummer wird von der Common Language Runtime zum Erzwingen von Versionsrichtlinien verwendet und spielt zur Laufzeit eine Schlüsselrolle im Vorgang der Typauflösung.  
  
- Eine Informationsversion, d. h. eine Zeichenfolge, die zusätzliche Versionsinformationen enthält und ausschließlich Informationszwecken dient.  
  
### <a name="assembly-version-number"></a>Assemblyversionsnummer  

Die Versionsnummer ist Teil der Identität einer Assembly. Daher betrachtet die Common Language Runtime zwei Assemblys mit unterschiedlichen Versionsnummern als zwei völlig verschiedene Assemblys. Diese Versionsnummer wird physisch als vierteilige Zeichenfolge im folgenden Format dargestellt:  
  
\<*hauptversion*>.\<*nebenversion*>.\<*buildnummer*>.\<*revision*>  
  
Die Version 1.5.1254.0 z. B. gibt 1 als Hauptversion, 5 als Nebenversion, 1254 als Buildnummer und 0 als Revisionsnummer an.  
  
Die Versionsnummer wird im Assemblymanifest zusammen mit anderen Informationen zur Identität gespeichert, einschließlich des Assemblynamens und des öffentlichen Schlüssels sowie der Informationen über Beziehungen und Identitäten anderer Assemblys, die mit der Anwendung verbunden sind.  
  
Beim Erstellen einer Assembly zeichnet das Entwicklungstool die Abhängigkeitsinformationen für jede Assembly auf, auf die im Assemblymanifest verwiesen wird. Die Laufzeit verwendet diese Versionsnummern zusammen mit den Konfigurationsinformationen, die von einem Administrator, einer Anwendung oder einem Herausgeber festgelegt wurden, um die richtige Version einer Assembly zu laden, auf die verwiesen wird.  
  
Die Laufzeit unterscheidet zum Zweck der Versionskontrolle zwischen normalen Assemblys und Assemblys mit starkem Namen. Die Version wird nur bei Assemblys mit starkem Namen überprüft.  
  
Weitere Informationen zum Festlegen von Versionsbindungsrichtlinien finden Sie unter [Konfigurieren von Apps](../../framework/configure-apps/index.md). Informationen darüber, wie die Runtime die Versionsinformationen bei der Suche nach einer bestimmten Assembly verwendet, finden Sie unter [So sucht die Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md).  
  
### <a name="assembly-informational-version"></a>Assemblyinformationsversion  

Die Informationsversion ist eine Zeichenfolge, die zusätzliche Versionsinformationen an eine Assembly anfügt und ausschließlich Informationszwecken dient. Die Informationen werden nicht zur Laufzeit verwendet. Die textbasierte Informationsversion entspricht dem Marketingtext des Produkts, der Verpackung oder dem Produktnamen und wird nicht zur Laufzeit verwendet. Eine Informationsversion könnte z. B. wie folgt lauten: "Common Language Runtime Version 1.0" oder "NET Control SP 2". Diese Angabe wird in Microsoft Windows im Eigenschaftendialogfeld der Datei auf der Registerkarte Version als Eintrag "Produktversion" angezeigt.  
  
> [!NOTE]
> Obwohl Sie einen beliebigen Text eingeben können, wird beim Kompilieren eine Warnung angezeigt, wenn die Zeichenfolge nicht das für die Versionsnummer der Assembly verwendete Format aufweist oder das Format zwar korrekt ist, die Zeichenfolge jedoch Platzhalterzeichen enthält. Sie können diese Warnung ignorieren.  
  
Die Informationsversion wird mit dem benutzerdefinierten Attribut <xref:System.Reflection.AssemblyInformationalVersionAttribute?displayProperty=nameWithType> dargestellt. Weitere Informationen über das Informationsversionsattribut finden Sie unter [Festlegen von Assemblyattributen](set-attributes.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [So sucht Common Language Runtime nach Assemblys](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurieren von Apps](../../framework/configure-apps/index.md)
- [Festlegen von Assemblyattributen](set-attributes.md)
- [Assemblys in .NET](index.md)
