---
title: Suchen der in einem lokalen System definierten Zeitzonen
description: Suchen der in einem lokalen System definierten Zeitzonen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3a6ee323-f3cf-486d-aa0c-103931f1eba9
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: e7f07a1f86ca31a24e25d98de2f8918ff098db24

---

# <a name="finding-the-time-zones-defined-on-a-local-system"></a>Suchen der in einem lokalen System definierten Zeitzonen

Die [System.TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse macht keinen öffentlichen Konstruktor verfügbar. Daher kann das `new`-Schlüsselwort nicht zum Erstellen eines neuen [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekts verwendet werden. Stattdessen werden [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekte durch Abrufen von Informationen über vordefinierte Zeitzonen aus dem Betriebssystem instanziiert. Dieses Thema behandelt die Instanziierung einer Zeitzone aus den im Betriebssystem gespeicherten Daten. Darüber hinaus ermöglichen die `static`-Eigenschaften (`Shared` in Visual Basic) der [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse Zugriff auf die koordinierte Weltzeit (Coordinated Universal Time, UTC) und die lokale Zeitzone.

## <a name="accessing-individual-time-zones"></a>Zugreifen auf einzelne Zeitzonen

Die [TimeZoneInfo](xref:System.TimeZoneInfo)-Klasse bietet zwei vordefinierte Zeitzonenobjekte, die die UTC-Zeit und die lokale Zeitzone darstellen. Sie werden über die Eigenschaften [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) bzw. [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) zur Verfügung gestellt. Anweisungen zum Zugreifen auf die UTC-Zeit oder die lokalen Zeitzonen finden Sie unter [Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](access-utc-and-local.md). 

Sie können auch ein [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekt instanziieren, das jede durch das Betriebssystem definierte Zeitzone darstellt. Anweisungen zum Instanziieren eines bestimmten Zeitzonenobjekts finden Sie unter [Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts](instantiate-time-zone-info.md).

## <a name="time-zone-identifiers"></a>Zeitzonenbezeichner

Der Zeitzonenbezeichner ist ein Schlüsselfeld, das die Zeitzone eindeutig identifiziert. Während die meisten Schlüssel relativ kurz sind, ist der Zeitzonenbezeichner vergleichsweise lang. In den meisten Fällen entspricht der dazugehörige Wert der [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName)-Eigenschaft, die zum Bereitstellen des Namens der Standardzeit für die Zeitzone verwendet wird. Es gibt jedoch auch Ausnahmen. Die beste Möglichkeit, um sicherzustellen, dass Sie einen gültigen Bezeichner angeben, besteht darin, die auf Ihrem System verfügbaren Zeitzonen aufzulisten und die dazugehörigen IDs zur Kenntnis zu nehmen. Anweisungen zum Aufzählen von Zeitzonen finden Sie unter [Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen](enumerate-time-zones.md).

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)

[Gewusst wie: Zugreifen auf die vordefinierte UTC und lokale Zeitzonenobjekte](access-utc-and-local.md)

[Gewusst wie: Instanziieren eines TimeZoneInfo-Objekts](instantiate-time-zone-info.md)

[Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen](enumerate-time-zones.md)

[Konvertieren von Uhrzeiten zwischen Zeitzonen](converting-between-time-zones.md)


<!--HONumber=Nov16_HO3-->


