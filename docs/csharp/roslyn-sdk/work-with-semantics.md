---
title: Arbeiten mit dem Semantikmodell für .NET Compiler Platform SDK
description: In dieser Übersicht werden die Typen vorgestellt, die Sie zum Verstehen und Bearbeiten von Semantikmodellen Ihres Codes verwenden.
ms.date: 10/15/2017
ms.custom: mvc
ms.openlocfilehash: 8575988cd98a4c0ba3f24107788f065f7472f55d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156934"
---
# <a name="work-with-semantics"></a>Arbeiten mit der Semantik

[Syntaxstrukturen](work-with-syntax.md) stellen die lexikalische und syntaktische Struktur des Quellcodes dar. Diese Informationen reichen zwar schon aus, um alle Deklarationen und die Logik in der Quelle zu beschreiben, jedoch reichen sie nicht aus, um Verweise zu ermitteln. Ein Name kann Folgendes darstellen:

- einen Typ
- ein Feld
- eine Methode
- eine lokale Variable

Zwar sind diese Elemente alle eindeutig, jedoch sind häufig tiefgreifende Kenntnisse über die Sprachregeln erforderlich, um zu bestimmen, auf welches Element ein Bezeichner verweist.

Im Quellcode werden Programmelemente dargestellt. Außerdem können Programme auf zuvor erstellte Bibliotheken verweisen, die in Assemblydateien gepackt wurden. Zwar ist kein Quellcode für Assemblys verfügbar, und daher auch keine Syntaxknoten oder -strukturen, jedoch können Programme auf Elemente innerhalb der Assemblys verweisen.

Für Aufgaben wie diese benötigen Sie das **Semantikmodell**.

Neben einem syntaktischen Modell des Quellcodes kapselt ein Semantikmodell die Sprachregeln, sodass Sie Bezeichner problemlos dem richtigen Programmelement zuordnen können, auf das verwiesen wird.

## <a name="compilation"></a>Kompilierung

Bei einer Kompilierung handelt es sich um eine Darstellung sämtlicher Elemente, die zum Kompilieren eines C#- oder Visual Basic-Programms benötigt werden. Dies umfasst alle Assemblyverweise, Compileroptionen und Quelldateien.

Da all diese Informationen an demselben Ort gespeichert sind, können die Elemente, die im Quellcode enthalten sind, detaillierter beschrieben werden. Die Kompilierung stellt sämtliche deklarierten Typen, Member oder Variablen als verschiedene Symbole dar. Sie enthält verschiedene Methoden, die Sie dabei unterstützen, Symbole, die entweder im Quellcode deklariert sind oder als Metadaten aus einer Assembly importiert wurden, zu finden und Beziehungen dazu herzustellen.

Ähnlich wie Syntaxstrukturen sind Kompilierungen unveränderlich. Nachdem Sie eine Kompilierung erstellt haben, kann diese weder von Ihnen noch von anderen Personen verändert werden, mit denen Sie sie teilen. Allerdings können Sie eine neue Kompilierung aus einer bereits vorhandenen erstellen und dabei Änderungen vornehmen. So können Sie z.B. eine Kompilierung erstellen, die einer bereits vorhandenen Kompilierung weitestgehend entspricht, aber eine zusätzliche Quelldatei oder einen zusätzlichen Quellverweis enthält.

## <a name="symbols"></a>Symbole

Ein Symbol stellt ein eindeutiges Element dar, das vom Quellcode deklariert wird oder aus einer Assembly als Metadatenelement importiert wird. Jeder einzelne Namespace, Typ, Parameter, jede einzelne Methode, Eigenschaft, lokale Variable und jedes einzelne Feld oder Ereignis wird von einem eigenen Symbol dargestellt.

Mithilfe verschiedener Methoden und Eigenschaften des <xref:Microsoft.CodeAnalysis.Compilation>-Typs können Sie Symbole finden. Beispielsweise können Sie ein Symbol für einen deklarierten Typ über einen allgemeinen Metadatennamen finden. Außerdem können Sie auf die gesamte Symboltabelle als Symbolstruktur zugreifen, deren Stamm der globale Namespace ist.

Außerdem enthalten Symbole zusätzliche Informationen, die der Compiler über die Quelle oder über Metadaten wie andere Symbole bestimmt, auf die verwiesen wird. Jede Art von Symbol wird von einer separaten Schnittstelle dargestellt, die von <xref:Microsoft.CodeAnalysis.ISymbol> abgeleitet wird. Dabei verfügt jedes Symbol über eigene Methoden und Eigenschaften, die die vom Compiler erfassten Informationen enthalten. Viele dieser Eigenschaften enthalten direkte Verweise auf andere Symbole. Beispielsweise verweist die <xref:Microsoft.CodeAnalysis.IMethodSymbol.ReturnType?displayProperty=nameWithType>-Eigenschaft auf das tatsächliche Symbol, auf das die Methodendeklaration verweist.

Symbole stehen für eine allgemeine Darstellungen von Namespaces, Typen und Mitgliedern zwischen Quellcode und Metadaten. Beispielsweise werden sowohl Methoden, die im Quellcode deklariert wurden, als auch Methoden, die aus Metadaten importiert wurden, von einem <xref:Microsoft.CodeAnalysis.IMethodSymbol> mit denselben Eigenschaften dargestellt.

Symbole haben ein ähnliches Konzept wie CLR-Typsysteme, die von der <xref:System.Reflection>-API dargestellt werden. Allerdings sind sie umfangreicher, da sie mehr als nur Typen modellieren. Namespaces, lokale Variablen und Bezeichnungen sind Symbole. Außerdem stellen Symbole keine CLR-Konzepte, sondern Sprachkonzepte dar. Es gibt also einige Überlappungen, aber es werden auch wichtige Unterschiede deutlich. Beispielsweise stellt eine Iteratormethode in C# oder Visual Basic ein einzelnes Symbol dar. Wenn die Iteratormethode allerdings in CLR-Metadaten übersetzt, handelt es sich dann um einen Typ und mehrere Methoden.

## <a name="semantic-model"></a>Semantikmodell

In einem Semantikmodell werden alle semantischen Informationen einer einzelnen Quelldatei dargestellt. Sie können es verwenden, um Folgendes zu ermitteln:

- Die Symbole, auf die an einer bestimmten Stelle in der Quelle verwiesen wird.
- Der resultierende Typ eines beliebigen Ausdrucks.
- Alle Diagnosen, bei denen es sich um Fehler oder Warnungen handelt.
- Die Art und Weise, wie Variablen in bestimmte Bereiche der Quelle hinein und wieder aus ihnen heraus fließen.
- Antworten auf Fragen mit spekulativem Charakter.
