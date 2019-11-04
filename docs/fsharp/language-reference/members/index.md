---
title: Member
description: Erfahren Sie mehr über Objektmember in der F# Programmiersprache.
ms.date: 05/16/2016
ms.openlocfilehash: 2e85d014cd1e9b7997638cb210fed5705c217719
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425069"
---
# <a name="members"></a>Member

Dieser Abschnitt beschreibt Member von F#-Objekttypen.

## <a name="remarks"></a>Hinweise

*Member* sind Funktionen, die Teil einer Typdefinition sind und mit dem Schlüsselwort `member` deklariert werden. F#-Objekttypen, z.B. Datensätze, Klassen, Unterscheidbare Unions, Schnittstellen und Strukturen,Klasse, unterstützen Elemente. Weitere Informationen finden Sie unter [Datensätze](../records.md), [Klassen](../classes.md), [Unterscheidungs-Unions](../discriminated-Unions.md), [Schnittstellen](../interfaces.md) und [Strukturen](../structures.md).

Elemente bilden in der Regel die öffentliche Schnittstelle für einen Typ, weshalb diese öffentlich sind, sofern nicht anders angegeben. Member können auch privat oder intern deklariert werden. Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-Control.md). Signaturen für Typen können auch verwendet werden, um bestimmte Member eines Typs verfügbar bzw. nicht verfügbar zu machen. Weitere Informationen finden Sie unter [Signaturen](../signature-files.md).

Private Felder und `do`-Bindungen, die nur mit Klassen verwendet werden, sind keine richtigen Member, da sie nicht teil der öffentlichen Schnittstelle eines Typs sind und nicht mit dem Schlüsselwort `member` deklariert sind. Sie werden jedoch auch in diesem Abschnitt beschrieben.

## <a name="related-topics"></a>Verwandte Themen

|Topic|Beschreibung|
|-----|-----------|
|[`let`-Bindungen in Klassen](let-bindings-in-classes.md)|Beschreibt die Definition der privaten Felder und Funktionen in Klassen.|
|[`do`-Bindungen in Klassen](do-bindings-in-classes.md)|Beschreibt die Spezifikation des Initialisierungscodes für Objekte.|
|[Eigenschaften](properties.md)|Beschreibt Eigenschaftenmember in Klassen und anderen Typen.|
|[Indizierte Eigenschaften](indexed-properties.md)|Beschreibt arrayähnliche Eigenschaften in Klassen und anderen Typen.|
|[Methoden](methods.md)|Beschreibt Funktionen, die Member eines Typs sind.|
|[Konstruktoren](constructors.md)|Beschreibt spezielle Funktionen, die Objekte eines Typs initialisieren.|
|[Operatorüberladung](../operator-overloading.md)|Beschreibt die Definition benutzerdefinierter Operatoren für Typen.|
|[Ereignisse](events.md)|Beschreibt die Definition von Ereignissen und Unterstützung für die Ereignisbehandlung in F#.|
|[Explizite Felder: Das `val`-Schlüsselwort](explicit-fields-the-val-keyword.md)|Beschreibt die Definition von nicht initialisierten Feldern in einem Typ.|
