---
title: Application-Einstellungsschema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schema application settings
- application settings, schema [Windows Forms]
- Windows Forms, application settings schema
- configuration schema [.NET Framework], application settings
ms.assetid: 5797fcff-6081-4e8c-bebf-63d9c70cf14b
caps.latest.revision: "3"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d93a18b17e0d6b8e413903fb84dc6b427d94f6af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="application-settings-schema"></a><span data-ttu-id="7b0e8-102">Application-Einstellungsschema</span><span class="sxs-lookup"><span data-stu-id="7b0e8-102">Application Settings schema</span></span>

<span data-ttu-id="7b0e8-103">Anwendungseinstellungen ermöglichen eine Windows Forms- oder ASP.NET-ANWENDUNGEN Anwendung speichern und Abrufen von anwendungsspezifische und benutzerspezifische Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-103">Application settings allow a Windows Forms or ASP.NET application to store and retrieve application-scoped and user-scoped settings.</span></span> <span data-ttu-id="7b0e8-104">In diesem Kontext eine *Einstellung* ist eine Information, die speziell für die Anwendung oder gelten speziell für den aktuellen Benutzer möglicherweise – alles von einer Datenbank-Verbindungszeichenfolge für den Benutzer bevorzugte Standard-Fenstergröße.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-104">In this context, a *setting* is any piece of information that may be specific to the application or specific to the current user — anything from a database connection string to the user's preferred default window size.</span></span>

<span data-ttu-id="7b0e8-105">Anwendungseinstellungen in einer Windows Forms-Anwendung verwendet standardmäßig die <xref:System.Configuration.LocalFileSettingsProvider> -Klasse, die das Konfigurationssystem .NET verwendet wird, um die Einstellungen in eine XML-Konfigurationsdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-105">By default, application settings in a Windows Forms application uses the <xref:System.Configuration.LocalFileSettingsProvider> class, which uses the .NET configuration system to store settings in an XML configuration file.</span></span> <span data-ttu-id="7b0e8-106">Weitere Informationen zu den Dateien, die von den Anwendungseinstellungen verwendet, finden Sie unter [Architektur der Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="7b0e8-106">For more information about the files used by application settings, see [Application Settings Architecture](~/docs/framework/winforms/advanced/application-settings-architecture.md).</span></span>

<span data-ttu-id="7b0e8-107">Die Anwendungseinstellungen definiert die folgenden Elemente im Rahmen der Konfigurationsdateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-107">Application settings defines the following elements as part of the configuration files it uses.</span></span>

| <span data-ttu-id="7b0e8-108">Element</span><span class="sxs-lookup"><span data-stu-id="7b0e8-108">Element</span></span>                    | <span data-ttu-id="7b0e8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b0e8-109">Description</span></span>                                                                           |
| -------------------------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="7b0e8-110">**\<ApplicationSettings >**</span><span class="sxs-lookup"><span data-stu-id="7b0e8-110">**\<applicationSettings>**</span></span> | <span data-ttu-id="7b0e8-111">Enthält alle  **\<Einstellung >** Tags, die für die Anwendung spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-111">Contains all **\<setting>** tags specific to the application.</span></span>                         |
| <span data-ttu-id="7b0e8-112">**\<UserSettings >**</span><span class="sxs-lookup"><span data-stu-id="7b0e8-112">**\<userSettings>**</span></span>        | <span data-ttu-id="7b0e8-113">Enthält alle  **\<Einstellung >** Tags für den aktuellen Benutzer spezifisch.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-113">Contains all **\<setting>** tags specific to the current user.</span></span>                        |
| <span data-ttu-id="7b0e8-114">**\<Festlegen von >**</span><span class="sxs-lookup"><span data-stu-id="7b0e8-114">**\<setting>**</span></span>             | <span data-ttu-id="7b0e8-115">Definiert eine Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-115">Defines a setting.</span></span> <span data-ttu-id="7b0e8-116">Untergeordnetes Element des  **\<ApplicationSettings >** oder  **\<UserSettings >**.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-116">Child of either **\<applicationSettings>** or **\<userSettings>**.</span></span> |
| <span data-ttu-id="7b0e8-117">**\<value>**</span><span class="sxs-lookup"><span data-stu-id="7b0e8-117">**\<value>**</span></span>               | <span data-ttu-id="7b0e8-118">Definiert eine Einstellung-Wert.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-118">Defines a setting's value.</span></span> <span data-ttu-id="7b0e8-119">Untergeordnetes Element des  **\<Einstellung >**.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-119">Child of **\<setting>**.</span></span>                                   |

## <a name="applicationsettings-element"></a><span data-ttu-id="7b0e8-120">\<ApplicationSettings >-Element</span><span class="sxs-lookup"><span data-stu-id="7b0e8-120">\<applicationSettings> element</span></span>

<span data-ttu-id="7b0e8-121">Dieses Element enthält alle  **\<Einstellung >** Tags, die mit einer Instanz von der Anwendung auf einem Clientcomputer spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-121">This element contains all **\<setting>** tags that are specific to an instance of the application on a client computer.</span></span> <span data-ttu-id="7b0e8-122">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-122">It defines no attributes.</span></span>

## <a name="usersettings-element"></a><span data-ttu-id="7b0e8-123">\<UserSettings >-Element</span><span class="sxs-lookup"><span data-stu-id="7b0e8-123">\<userSettings> element</span></span>

<span data-ttu-id="7b0e8-124">Dieses Element enthält alle  **\<Einstellung >** Transpondern, die für den Benutzer spezifisch sind, der die Anwendung derzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-124">This element contains all **\<setting>** tags that are specific to the user who is currently using the application.</span></span> <span data-ttu-id="7b0e8-125">Es definiert keine Attribute.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-125">It defines no attributes.</span></span>

## <a name="setting-element"></a><span data-ttu-id="7b0e8-126">\<Festlegen von >-Element</span><span class="sxs-lookup"><span data-stu-id="7b0e8-126">\<setting> element</span></span>

<span data-ttu-id="7b0e8-127">Dieses Element definiert eine Einstellung an.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-127">This element defines a setting.</span></span> <span data-ttu-id="7b0e8-128">Es weist folgende Attribute.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-128">It has the following attributes.</span></span>

| <span data-ttu-id="7b0e8-129">Attribut</span><span class="sxs-lookup"><span data-stu-id="7b0e8-129">Attribute</span></span>        | <span data-ttu-id="7b0e8-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b0e8-130">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="7b0e8-131">**name**</span><span class="sxs-lookup"><span data-stu-id="7b0e8-131">**name**</span></span>         | <span data-ttu-id="7b0e8-132">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-132">Required.</span></span> <span data-ttu-id="7b0e8-133">Die eindeutige ID der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-133">The unique ID of the setting.</span></span> <span data-ttu-id="7b0e8-134">Einstellungen, die in der Visual Studio erstellt werden gespeichert, mit dem Namen `ProjectName.Properties.Settings`.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-134">Settings created through Visual Studio are saved with the name `ProjectName.Properties.Settings`.</span></span> |
| <span data-ttu-id="7b0e8-135">**serializedAs**</span><span class="sxs-lookup"><span data-stu-id="7b0e8-135">**serializedAs**</span></span> | <span data-ttu-id="7b0e8-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-136">Required.</span></span> <span data-ttu-id="7b0e8-137">Das Format, das zum Serialisieren des Wertes in Text.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-137">The format to use for serializing the value to text.</span></span> <span data-ttu-id="7b0e8-138">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7b0e8-138">Valid values are:</span></span><br><br><span data-ttu-id="7b0e8-139">- `string`.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-139">- `string`.</span></span> <span data-ttu-id="7b0e8-140">Der Wert wird als eine Zeichenfolge mit serialisiert eine <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-140">The value is serialized as a string using a <xref:System.ComponentModel.TypeConverter>.</span></span><br><span data-ttu-id="7b0e8-141">- `xml`.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-141">- `xml`.</span></span> <span data-ttu-id="7b0e8-142">Der Wert wird mithilfe von XML-Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-142">The value is serialized using XML serialization.</span></span><br><span data-ttu-id="7b0e8-143">- `binary`.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-143">- `binary`.</span></span> <span data-ttu-id="7b0e8-144">Der Wert wird als Text-codierte Binärdaten mit binärer Serialisierung serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-144">The value is serialized as text-encoded binary using binary serialization.</span></span><br /><span data-ttu-id="7b0e8-145">- `custom`.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-145">- `custom`.</span></span> <span data-ttu-id="7b0e8-146">Der Einstellungsanbieter Kenntnisse von dieser Einstellung hat und serialisiert und deserialisiert serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-146">The settings provider has inherent knowledge of this setting and serializes and de-serializes it.</span></span> |

## <a name="value-element"></a><span data-ttu-id="7b0e8-147">\<Wert >-Element</span><span class="sxs-lookup"><span data-stu-id="7b0e8-147">\<value> element</span></span>

<span data-ttu-id="7b0e8-148">Dieses Element enthält den Wert einer Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7b0e8-148">This element contains the value of a setting.</span></span>

## <a name="example"></a><span data-ttu-id="7b0e8-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b0e8-149">Example</span></span>

<span data-ttu-id="7b0e8-150">Das folgende Beispiel zeigt eine Einstellungen Anwendungsdatei, die zwei anwendungsspezifische Einstellungen und zwei benutzerspezifische Einstellungen definiert:</span><span class="sxs-lookup"><span data-stu-id="7b0e8-150">The following example shows an application settings file that defines two application-scoped settings and two user-scoped settings:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="applicationSettings" type="System.Configuration.ApplicationSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
    </sectionGroup>
    <sectionGroup name="userSettings" type="System.Configuration.UserSettingsGroup, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="WindowsApplication1.Properties.Settings" type="System.Configuration.ClientSettingsSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" allowExeDefinition="MachineToLocalUser" />
    </sectionGroup>
  </configSections>
  <applicationSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="Cursor" serializeAs="String">
        <value>Default</value>
      </setting>
      <setting name="DoubleBuffering" serializeAs="String">
        <value>False</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </applicationSettings>
  <userSettings>
    <WindowsApplication1.Properties.Settings>
      <setting name="FormTitle" serializeAs="String">
        <value>Form1</value>
      </setting>
      <setting name="FormSize" serializeAs="String">
        <value>595, 536</value>
      </setting>
    </WindowsApplication1.Properties.Settings>
  </userSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7b0e8-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b0e8-151">See also</span></span>

<span data-ttu-id="7b0e8-152">[Übersicht über Anwendungseinstellungen](~/docs/framework/winforms/advanced/application-settings-overview.md) </span><span class="sxs-lookup"><span data-stu-id="7b0e8-152">[Application Settings Overview](~/docs/framework/winforms/advanced/application-settings-overview.md) </span></span>  
[<span data-ttu-id="7b0e8-153">Architektur der Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="7b0e8-153">Application Settings Architecture</span></span>](~/docs/framework/winforms/advanced/application-settings-architecture.md)
