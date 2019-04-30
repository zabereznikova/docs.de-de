---
title: Member
description: Erfahren Sie mehr über die Member des Objekts in der F# Programmiersprache.
ms.date: 05/16/2016
ms.openlocfilehash: c32bd76ab60673563f0cc45ce0fb569b2ea262b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903850"
---
# <a name="members"></a>Member

Dieser Abschnitt beschreibt Member von F#-Objekttypen.

## <a name="remarks"></a>Hinweise

*Member* sind Funktionen, die Teil einer Typdefinition sind und mit dem Schlüsselwort `member` deklariert werden. F#-Objekttypen, z.B. Datensätze, Klassen, Unterscheidbare Unions, Schnittstellen und Strukturen,Klasse, unterstützen Elemente. Weitere Informationen finden Sie unter [Datensätze](../records.md), [Klassen](../classes.md), [Unterscheidungs-Unions](../discriminated-Unions.md), [Schnittstellen](../interfaces.md) und [Strukturen](../structures.md).

Elemente bilden in der Regel die öffentliche Schnittstelle für einen Typ, weshalb diese öffentlich sind, sofern nicht anders angegeben. Member können auch privat oder intern deklariert werden. Weitere Informationen finden Sie unter [Zugriffssteuerung](../access-Control.md). Signaturen für Typen können auch verwendet werden, um bestimmte Member eines Typs verfügbar bzw. nicht verfügbar zu machen. Weitere Informationen finden Sie unter [Signaturen](../signatures.md).

Private Felder und `do`-Bindungen, die nur mit Klassen verwendet werden, sind keine richtigen Member, da sie nicht teil der öffentlichen Schnittstelle eines Typs sind und nicht mit dem Schlüsselwort `member` deklariert sind. Sie werden jedoch auch in diesem Abschnitt beschrieben.

## <a name="related-topics"></a>Verwandte Themen

|Thema|Beschreibung|
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