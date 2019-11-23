---
title: <clear>-Element für <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a45572d0dcb2737558e11f5c38ac2ccc338c754a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119082"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="8cbab-102">\<> Element für \<configabschnitts löschen ></span><span class="sxs-lookup"><span data-stu-id="8cbab-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="8cbab-103">Löscht alle zuvor definierten Abschnitte und Abschnitts Gruppen.</span><span class="sxs-lookup"><span data-stu-id="8cbab-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="8cbab-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="8cbab-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="8cbab-105">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="8cbab-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="8cbab-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<löschen >**</span><span class="sxs-lookup"><span data-stu-id="8cbab-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8cbab-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8cbab-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="8cbab-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="8cbab-108">Attribute</span></span>

|           | <span data-ttu-id="8cbab-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cbab-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8cbab-110">**name**</span><span class="sxs-lookup"><span data-stu-id="8cbab-110">**name**</span></span>  | <span data-ttu-id="8cbab-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="8cbab-111">Required attribute.</span></span><br><br><span data-ttu-id="8cbab-112">Gibt den Namen des Abschnitts oder der Abschnitts Gruppe an, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8cbab-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="8cbab-113">Übergeordnetes Element</span><span class="sxs-lookup"><span data-stu-id="8cbab-113">Parent element</span></span>

|     | <span data-ttu-id="8cbab-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cbab-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8cbab-115"> **\<configSections>** Element</span><span class="sxs-lookup"><span data-stu-id="8cbab-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="8cbab-116">Enthält Konfigurations Abschnitts-und Namespace Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="8cbab-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8cbab-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8cbab-117">Child elements</span></span>

<span data-ttu-id="8cbab-118">Keine</span><span class="sxs-lookup"><span data-stu-id="8cbab-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="8cbab-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8cbab-119">Remarks</span></span>

<span data-ttu-id="8cbab-120">Das **\<Clear >** -Element entfernt alle Abschnitte und Abschnitts Gruppen aus der Anwendung, die zuvor in der aktuellen Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationsdatei Hierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8cbab-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="8cbab-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8cbab-121">Example</span></span>

<span data-ttu-id="8cbab-122">In diesem Beispiel werden eine Computer Konfigurationsdatei und eine Anwendungs Konfigurationsdatei definiert. Außerdem wird gezeigt, wie das **\<Clear >** -Element in einer Anwendungs Konfigurationsdatei verwendet wird, um die zuvor in der Computer Konfigurationsdatei definierten Abschnitte zu löschen</span><span class="sxs-lookup"><span data-stu-id="8cbab-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="8cbab-123">Der folgende Computer Konfigurationsdatei-Code deklariert zwei Abschnitte, **\<sampleSection >** und **\<anotherSampleSection->** , die vor der Anwendungs Konfigurationsdatei gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="8cbab-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="8cbab-124">Der folgende Anwendungs Konfigurationsdatei-Code löscht alle zuvor deklarierten Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="8cbab-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="8cbab-125">Die Anwendung kann in keinem der Abschnitte, die in der Computer Konfigurationsdatei deklariert wurden, Einstellungen verwenden oder abrufen.</span><span class="sxs-lookup"><span data-stu-id="8cbab-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="8cbab-126">Es können jedoch Einstellungen aus **\<anotherSection->** verwendet werden, da es nach dem **\<Clear >** -Element liegt.</span><span class="sxs-lookup"><span data-stu-id="8cbab-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="8cbab-127">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="8cbab-127">Configuration file</span></span>

<span data-ttu-id="8cbab-128">Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.</span><span class="sxs-lookup"><span data-stu-id="8cbab-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8cbab-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cbab-129">See also</span></span>

- [<span data-ttu-id="8cbab-130">Konfigurationsdatei Schema für die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8cbab-130">Configuration file schema for the .NET Framework</span></span>](index.md)
