---
title: "Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen"
description: "Aufzählen der auf einem Computer vorhandenen Zeitzonen"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c5ae4a6c-1790-4355-b5b1-879aaf956129
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f30ba2a483ff7e5867417969946c2774175d5e3d
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Gewusst wie: Aufzählen der auf einem Computer vorhandenen Zeitzonen

Für die erfolgreiche Verarbeitung einer Zeitzone ist es erforderlich, dass dem System Informationen zu dieser Zeitzone zur Verfügung stehen. Windows-Betriebssysteme beispielsweise speichern diese Informationen in der Registrierung. Es gibt zwar sehr viele Zeitzonen auf der Welt, die Registrierung enthält aber nur Informationen zu einigen davon. Darüber hinaus ist die Registrierung selbst eine dynamische Struktur, deren Inhalt absichtlich oder aus Versehen geändert werden kann. Daher kann eine Anwendung nicht voraussetzen, dass eine bestimmte Zeitzone in einem System definiert und verfügbar ist. Bei vielen Anwendungen, die Zeitzoneninformationen verwenden, besteht der erste Schritt darin zu ermitteln, ob die erforderlichen Zeitzonen im lokalen System verfügbar sind, oder dem Benutzer eine Liste der Zeitzonen zur Auswahl zu bieten. Dafür wiederum muss eine Anwendung die im lokalen System definierten Zeitzonen aufzählen können. 

## <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Aufzählen der im lokalen System vorhandenen Zeitzonen

1. Rufen Sie die [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones)-Methode auf. Die Methode gibt eine allgemeine [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601)-Auflistung von [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekten zurück. Die Einträge in der Auflistung sind nach ihrer [DisplayName](xref:System.TimeZoneInfo.DisplayName)-Eigenschaft sortiert. Zum Beispiel:

    ```csharp
    ReadOnlyCollection<TimeZoneInfo> tzCollection;
    tzCollection = TimeZoneInfo.GetSystemTimeZones();
    ```

    ```vb
    Dim tzCollection As ReadOnlyCollection(Of TimeZoneInfo) = TimeZoneInfo.GetSystemTimeZones
    ```

2. Zählen Sie die einzelnen [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekte in der Auflistung auf, indem Sie eine `foreach`-Schleife (in C#) oder eine `For Each…Next`-Schleife (in Visual Basic) verwenden und alle erforderlichen Verarbeitungsschritte für jedes Objekt ausführen. Der folgende Code zählt beispielsweise die [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601)-Auflistung von [TimeZoneInfo](xref:System.TimeZoneInfo)-Objekten auf, die in Schritt 1 zurückgegeben wurden, und gibt den Anzeigenamen jeder Zeitzone in der Konsole aus.

    ```csharp
    foreach (TimeZoneInfo timeZone in tzCollection)
    Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName);
    ```

    ```vb
    For Each timeZone As TimeZoneInfo In tzCollection
        Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName)
    Next
    ```

## <a name="see-also"></a>Siehe auch

[Datumsangaben, Uhrzeiten und Zeitzonen](index.md)

[Suchen der in einem lokalen System definierten Zeitzonen](finding-the-time-zones-on-local-system.md)


