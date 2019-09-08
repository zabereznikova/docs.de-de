---
title: ODBC-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794718"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="2e8e3-102">ODBC-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="2e8e3-102">ODBC Schema Collections</span></span>

<span data-ttu-id="2e8e3-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="2e8e3-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="2e8e3-104">Microsoft SQL Server-ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="2e8e3-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="2e8e3-105">Der Microsoft SQL Server ODBC-Treiber unterstützt neben den allgemeinen Schema Auflistungen auch die folgenden spezifischen Schema Auflistungen:</span><span class="sxs-lookup"><span data-stu-id="2e8e3-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="2e8e3-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="2e8e3-106">Tables</span></span>

- <span data-ttu-id="2e8e3-107">Indizes</span><span class="sxs-lookup"><span data-stu-id="2e8e3-107">Indexes</span></span>

- <span data-ttu-id="2e8e3-108">Spalten</span><span class="sxs-lookup"><span data-stu-id="2e8e3-108">Columns</span></span>

- <span data-ttu-id="2e8e3-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2e8e3-109">Procedures</span></span>

- <span data-ttu-id="2e8e3-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2e8e3-110">ProcedureColumns</span></span>

- <span data-ttu-id="2e8e3-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2e8e3-111">ProcedureParameters</span></span>

- <span data-ttu-id="2e8e3-112">Ansichten</span><span class="sxs-lookup"><span data-stu-id="2e8e3-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="2e8e3-113">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="2e8e3-113">Tables and Views</span></span>

|<span data-ttu-id="2e8e3-114">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-114">ColumnName</span></span>|<span data-ttu-id="2e8e3-115">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="2e8e3-116">TABLE_CAT</span></span>|<span data-ttu-id="2e8e3-117">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-117">String</span></span>|
|<span data-ttu-id="2e8e3-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="2e8e3-118">TABLE_SCHEM</span></span>|<span data-ttu-id="2e8e3-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-119">String</span></span>|
|<span data-ttu-id="2e8e3-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-120">TABLE_NAME</span></span>|<span data-ttu-id="2e8e3-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-121">String</span></span>|
|<span data-ttu-id="2e8e3-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-122">TABLE_TYPE</span></span>|<span data-ttu-id="2e8e3-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-123">String</span></span>|
|<span data-ttu-id="2e8e3-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-124">REMARKS</span></span>|<span data-ttu-id="2e8e3-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="2e8e3-126">Indizes</span><span class="sxs-lookup"><span data-stu-id="2e8e3-126">Indexes</span></span>

|<span data-ttu-id="2e8e3-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-127">ColumnName</span></span>|<span data-ttu-id="2e8e3-128">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="2e8e3-129">TABLE_CAT</span></span>|<span data-ttu-id="2e8e3-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-130">String</span></span>|
|<span data-ttu-id="2e8e3-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="2e8e3-131">TABLE_SCHEM</span></span>|<span data-ttu-id="2e8e3-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-132">String</span></span>|
|<span data-ttu-id="2e8e3-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-133">TABLE_NAME</span></span>|<span data-ttu-id="2e8e3-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-134">String</span></span>|
|<span data-ttu-id="2e8e3-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-135">NON_UNIQUE</span></span>|<span data-ttu-id="2e8e3-136">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-136">Int16</span></span>|
|<span data-ttu-id="2e8e3-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="2e8e3-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-138">String</span></span>|
|<span data-ttu-id="2e8e3-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-139">INDEX_NAME</span></span>|<span data-ttu-id="2e8e3-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-140">String</span></span>|
|<span data-ttu-id="2e8e3-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-141">TYPE</span></span>|<span data-ttu-id="2e8e3-142">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-142">Int16</span></span>|
|<span data-ttu-id="2e8e3-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="2e8e3-144">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-144">Int16</span></span>|
|<span data-ttu-id="2e8e3-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-145">COLUMN_NAME</span></span>|<span data-ttu-id="2e8e3-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-146">String</span></span>|
|<span data-ttu-id="2e8e3-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="2e8e3-147">ASC_OR_DESC</span></span>|<span data-ttu-id="2e8e3-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-148">String</span></span>|
|<span data-ttu-id="2e8e3-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="2e8e3-149">CARDINALITY</span></span>|<span data-ttu-id="2e8e3-150">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-150">Int32</span></span>|
|<span data-ttu-id="2e8e3-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="2e8e3-151">PAGES</span></span>|<span data-ttu-id="2e8e3-152">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-152">Int32</span></span>|
|<span data-ttu-id="2e8e3-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-153">FILTER_CONDITION</span></span>|<span data-ttu-id="2e8e3-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-154">String</span></span>|
|<span data-ttu-id="2e8e3-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2e8e3-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="2e8e3-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-156">String</span></span>|
|<span data-ttu-id="2e8e3-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-158">Byte</span><span class="sxs-lookup"><span data-stu-id="2e8e3-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="2e8e3-159">Spalten</span><span class="sxs-lookup"><span data-stu-id="2e8e3-159">Columns</span></span>

|<span data-ttu-id="2e8e3-160">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-160">ColumnName</span></span>|<span data-ttu-id="2e8e3-161">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="2e8e3-162">TABLE_CAT</span></span>|<span data-ttu-id="2e8e3-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-163">String</span></span>|
|<span data-ttu-id="2e8e3-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="2e8e3-164">TABLE_SCHEM</span></span>|<span data-ttu-id="2e8e3-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-165">String</span></span>|
|<span data-ttu-id="2e8e3-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-166">TABLE_NAME</span></span>|<span data-ttu-id="2e8e3-167">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-167">String</span></span>|
|<span data-ttu-id="2e8e3-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-168">COLUMN_NAME</span></span>|<span data-ttu-id="2e8e3-169">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-169">String</span></span>|
|<span data-ttu-id="2e8e3-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-170">DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-171">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-171">Int16</span></span>|
|<span data-ttu-id="2e8e3-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-172">TYPE_NAME</span></span>|<span data-ttu-id="2e8e3-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-173">String</span></span>|
|<span data-ttu-id="2e8e3-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-174">COLUMN_SIZE</span></span>|<span data-ttu-id="2e8e3-175">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-175">Int32</span></span>|
|<span data-ttu-id="2e8e3-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="2e8e3-177">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-177">Int32</span></span>|
|<span data-ttu-id="2e8e3-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="2e8e3-179">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-179">Int16</span></span>|
|<span data-ttu-id="2e8e3-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="2e8e3-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="2e8e3-181">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-181">Int16</span></span>|
|<span data-ttu-id="2e8e3-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-182">NULLABLE</span></span>|<span data-ttu-id="2e8e3-183">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-183">Int16</span></span>|
|<span data-ttu-id="2e8e3-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-184">REMARKS</span></span>|<span data-ttu-id="2e8e3-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-185">String</span></span>|
|<span data-ttu-id="2e8e3-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="2e8e3-186">COLUMN_DEF</span></span>|<span data-ttu-id="2e8e3-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-187">String</span></span>|
|<span data-ttu-id="2e8e3-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-189">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-189">Int16</span></span>|
|<span data-ttu-id="2e8e3-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="2e8e3-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="2e8e3-191">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-191">Int16</span></span>|
|<span data-ttu-id="2e8e3-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="2e8e3-193">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-193">Int32</span></span>|
|<span data-ttu-id="2e8e3-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="2e8e3-195">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-195">Int32</span></span>|
|<span data-ttu-id="2e8e3-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-196">IS_NULLABLE</span></span>|<span data-ttu-id="2e8e3-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-197">String</span></span>|
|<span data-ttu-id="2e8e3-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2e8e3-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="2e8e3-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-199">String</span></span>|
|<span data-ttu-id="2e8e3-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2e8e3-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="2e8e3-201">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-201">String</span></span>|
|<span data-ttu-id="2e8e3-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-203">Byte</span><span class="sxs-lookup"><span data-stu-id="2e8e3-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="2e8e3-204">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2e8e3-204">Procedures</span></span>

|<span data-ttu-id="2e8e3-205">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-205">ColumnName</span></span>|<span data-ttu-id="2e8e3-206">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="2e8e3-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="2e8e3-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-208">String</span></span>|
|<span data-ttu-id="2e8e3-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="2e8e3-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="2e8e3-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-210">String</span></span>|
|<span data-ttu-id="2e8e3-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="2e8e3-212">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-212">String</span></span>|
|<span data-ttu-id="2e8e3-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="2e8e3-214">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-214">Int32</span></span>|
|<span data-ttu-id="2e8e3-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="2e8e3-216">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-216">Int32</span></span>|
|<span data-ttu-id="2e8e3-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="2e8e3-218">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-218">Int32</span></span>|
|<span data-ttu-id="2e8e3-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-219">REMARKS</span></span>|<span data-ttu-id="2e8e3-220">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-220">String</span></span>|
|<span data-ttu-id="2e8e3-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2e8e3-222">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="2e8e3-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2e8e3-223">ProcedureColumns</span></span>

|<span data-ttu-id="2e8e3-224">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-224">ColumnName</span></span>|<span data-ttu-id="2e8e3-225">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="2e8e3-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="2e8e3-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-227">String</span></span>|
|<span data-ttu-id="2e8e3-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="2e8e3-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="2e8e3-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-229">String</span></span>|
|<span data-ttu-id="2e8e3-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="2e8e3-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-231">String</span></span>|
|<span data-ttu-id="2e8e3-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-232">COLUMN_NAME</span></span>|<span data-ttu-id="2e8e3-233">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-233">String</span></span>|
|<span data-ttu-id="2e8e3-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-234">COLUMN_TYPE</span></span>|<span data-ttu-id="2e8e3-235">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-235">Int16</span></span>|
|<span data-ttu-id="2e8e3-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-236">DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-237">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-237">Int16</span></span>|
|<span data-ttu-id="2e8e3-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-238">TYPE_NAME</span></span>|<span data-ttu-id="2e8e3-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-239">String</span></span>|
|<span data-ttu-id="2e8e3-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-240">COLUMN_SIZE</span></span>|<span data-ttu-id="2e8e3-241">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-241">Int32</span></span>|
|<span data-ttu-id="2e8e3-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="2e8e3-243">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-243">Int32</span></span>|
|<span data-ttu-id="2e8e3-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="2e8e3-245">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-245">Int16</span></span>|
|<span data-ttu-id="2e8e3-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="2e8e3-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="2e8e3-247">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-247">Int16</span></span>|
|<span data-ttu-id="2e8e3-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-248">NULLABLE</span></span>|<span data-ttu-id="2e8e3-249">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-249">Int16</span></span>|
|<span data-ttu-id="2e8e3-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-250">REMARKS</span></span>|<span data-ttu-id="2e8e3-251">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-251">String</span></span>|
|<span data-ttu-id="2e8e3-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="2e8e3-252">COLUMN_DEF</span></span>|<span data-ttu-id="2e8e3-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-253">String</span></span>|
|<span data-ttu-id="2e8e3-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-255">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-255">Int16</span></span>|
|<span data-ttu-id="2e8e3-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="2e8e3-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="2e8e3-257">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-257">Int16</span></span>|
|<span data-ttu-id="2e8e3-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="2e8e3-259">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-259">Int32</span></span>|
|<span data-ttu-id="2e8e3-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="2e8e3-261">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-261">Int32</span></span>|
|<span data-ttu-id="2e8e3-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-262">IS_NULLABLE</span></span>|<span data-ttu-id="2e8e3-263">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-263">String</span></span>|
|<span data-ttu-id="2e8e3-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2e8e3-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="2e8e3-265">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-265">String</span></span>|
|<span data-ttu-id="2e8e3-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2e8e3-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="2e8e3-267">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-267">String</span></span>|
|<span data-ttu-id="2e8e3-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-269">Byte</span><span class="sxs-lookup"><span data-stu-id="2e8e3-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="2e8e3-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2e8e3-270">ProcedureParameters</span></span>

|<span data-ttu-id="2e8e3-271">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-271">ColumnName</span></span>|<span data-ttu-id="2e8e3-272">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="2e8e3-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="2e8e3-274">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-274">String</span></span>|
|<span data-ttu-id="2e8e3-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="2e8e3-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="2e8e3-276">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-276">String</span></span>|
|<span data-ttu-id="2e8e3-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="2e8e3-278">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-278">String</span></span>|
|<span data-ttu-id="2e8e3-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-279">COLUMN_NAME</span></span>|<span data-ttu-id="2e8e3-280">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-280">String</span></span>|
|<span data-ttu-id="2e8e3-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-281">COLUMN_TYPE</span></span>|<span data-ttu-id="2e8e3-282">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-282">Int16</span></span>|
|<span data-ttu-id="2e8e3-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-283">DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-284">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-284">Int16</span></span>|
|<span data-ttu-id="2e8e3-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-285">TYPE_NAME</span></span>|<span data-ttu-id="2e8e3-286">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-286">String</span></span>|
|<span data-ttu-id="2e8e3-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-287">COLUMN_SIZE</span></span>|<span data-ttu-id="2e8e3-288">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-288">Int32</span></span>|
|<span data-ttu-id="2e8e3-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="2e8e3-290">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-290">Int32</span></span>|
|<span data-ttu-id="2e8e3-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="2e8e3-292">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-292">Int16</span></span>|
|<span data-ttu-id="2e8e3-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="2e8e3-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="2e8e3-294">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-294">Int16</span></span>|
|<span data-ttu-id="2e8e3-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-295">NULLABLE</span></span>|<span data-ttu-id="2e8e3-296">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-296">Int16</span></span>|
|<span data-ttu-id="2e8e3-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-297">REMARKS</span></span>|<span data-ttu-id="2e8e3-298">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-298">String</span></span>|
|<span data-ttu-id="2e8e3-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="2e8e3-299">COLUMN_DEF</span></span>|<span data-ttu-id="2e8e3-300">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-300">String</span></span>|
|<span data-ttu-id="2e8e3-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-302">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-302">Int16</span></span>|
|<span data-ttu-id="2e8e3-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="2e8e3-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="2e8e3-304">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-304">Int16</span></span>|
|<span data-ttu-id="2e8e3-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="2e8e3-306">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-306">Int32</span></span>|
|<span data-ttu-id="2e8e3-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="2e8e3-308">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-308">Int32</span></span>|
|<span data-ttu-id="2e8e3-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-309">IS_NULLABLE</span></span>|<span data-ttu-id="2e8e3-310">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-310">String</span></span>|
|<span data-ttu-id="2e8e3-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="2e8e3-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="2e8e3-312">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-312">String</span></span>|
|<span data-ttu-id="2e8e3-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2e8e3-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="2e8e3-314">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-314">String</span></span>|
|<span data-ttu-id="2e8e3-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-316">Byte</span><span class="sxs-lookup"><span data-stu-id="2e8e3-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="2e8e3-317">Microsoft Oracle ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="2e8e3-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="2e8e3-318">Der Microsoft SQL Server Oracle ODBC-Treiber unterstützt neben den allgemeinen Schema Auflistungen auch die folgenden spezifischen Schema Auflistungen:</span><span class="sxs-lookup"><span data-stu-id="2e8e3-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="2e8e3-319">Tabellen</span><span class="sxs-lookup"><span data-stu-id="2e8e3-319">Tables</span></span>

- <span data-ttu-id="2e8e3-320">Spalten</span><span class="sxs-lookup"><span data-stu-id="2e8e3-320">Columns</span></span>

- <span data-ttu-id="2e8e3-321">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2e8e3-321">Procedures</span></span>

- <span data-ttu-id="2e8e3-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2e8e3-322">ProcedureColumns</span></span>

- <span data-ttu-id="2e8e3-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2e8e3-323">ProcedureParameters</span></span>

- <span data-ttu-id="2e8e3-324">Ansichten</span><span class="sxs-lookup"><span data-stu-id="2e8e3-324">Views</span></span>

- <span data-ttu-id="2e8e3-325">Indizes</span><span class="sxs-lookup"><span data-stu-id="2e8e3-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="2e8e3-326">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="2e8e3-326">Tables and Views</span></span>

|<span data-ttu-id="2e8e3-327">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-327">ColumnName</span></span>|<span data-ttu-id="2e8e3-328">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="2e8e3-330">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-330">String</span></span>|
|<span data-ttu-id="2e8e3-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-331">TABLE_OWNER</span></span>|<span data-ttu-id="2e8e3-332">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-332">String</span></span>|
|<span data-ttu-id="2e8e3-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-333">TABLE_NAME</span></span>|<span data-ttu-id="2e8e3-334">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-334">String</span></span>|
|<span data-ttu-id="2e8e3-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-335">TABLE_TYPE</span></span>|<span data-ttu-id="2e8e3-336">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-336">String</span></span>|
|<span data-ttu-id="2e8e3-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-337">REMARKS</span></span>|<span data-ttu-id="2e8e3-338">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="2e8e3-339">Spalten</span><span class="sxs-lookup"><span data-stu-id="2e8e3-339">Columns</span></span>

|<span data-ttu-id="2e8e3-340">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-340">ColumnName</span></span>|<span data-ttu-id="2e8e3-341">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="2e8e3-343">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-343">String</span></span>|
|<span data-ttu-id="2e8e3-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-344">TABLE_OWNER</span></span>|<span data-ttu-id="2e8e3-345">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-345">String</span></span>|
|<span data-ttu-id="2e8e3-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-346">TABLE_NAME</span></span>|<span data-ttu-id="2e8e3-347">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-347">String</span></span>|
|<span data-ttu-id="2e8e3-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-348">COLUMN_NAME</span></span>|<span data-ttu-id="2e8e3-349">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-349">String</span></span>|
|<span data-ttu-id="2e8e3-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-350">DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-351">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-351">Int16</span></span>|
|<span data-ttu-id="2e8e3-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-352">TYPE_NAME</span></span>|<span data-ttu-id="2e8e3-353">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-353">String</span></span>|
|<span data-ttu-id="2e8e3-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-354">PRECISION</span></span>|<span data-ttu-id="2e8e3-355">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-355">Int32</span></span>|
|<span data-ttu-id="2e8e3-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-356">LENGTH</span></span>|<span data-ttu-id="2e8e3-357">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-357">Int32</span></span>|
|<span data-ttu-id="2e8e3-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-358">SCALE</span></span>|<span data-ttu-id="2e8e3-359">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-359">Int16</span></span>|
|<span data-ttu-id="2e8e3-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="2e8e3-360">RADIX</span></span>|<span data-ttu-id="2e8e3-361">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-361">Int16</span></span>|
|<span data-ttu-id="2e8e3-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-362">NULLABLE</span></span>|<span data-ttu-id="2e8e3-363">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-363">Int16</span></span>|
|<span data-ttu-id="2e8e3-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-364">REMARKS</span></span>|<span data-ttu-id="2e8e3-365">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-365">String</span></span>|
|<span data-ttu-id="2e8e3-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="2e8e3-367">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="2e8e3-368">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2e8e3-368">Procedures</span></span>

|<span data-ttu-id="2e8e3-369">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-369">ColumnName</span></span>|<span data-ttu-id="2e8e3-370">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="2e8e3-372">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-372">String</span></span>|
|<span data-ttu-id="2e8e3-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="2e8e3-374">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-374">String</span></span>|
|<span data-ttu-id="2e8e3-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="2e8e3-376">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-376">String</span></span>|
|<span data-ttu-id="2e8e3-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="2e8e3-378">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-378">Int16</span></span>|
|<span data-ttu-id="2e8e3-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="2e8e3-380">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-380">Int16</span></span>|
|<span data-ttu-id="2e8e3-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="2e8e3-382">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-382">Int16</span></span>|
|<span data-ttu-id="2e8e3-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-383">REMARKS</span></span>|<span data-ttu-id="2e8e3-384">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-384">String</span></span>|
|<span data-ttu-id="2e8e3-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2e8e3-386">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="2e8e3-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2e8e3-387">ProcedureColumns</span></span>

|<span data-ttu-id="2e8e3-388">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-388">ColumnName</span></span>|<span data-ttu-id="2e8e3-389">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="2e8e3-391">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-391">String</span></span>|
|<span data-ttu-id="2e8e3-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="2e8e3-393">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-393">String</span></span>|
|<span data-ttu-id="2e8e3-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="2e8e3-395">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-395">String</span></span>|
|<span data-ttu-id="2e8e3-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-396">COLUMN_NAME</span></span>|<span data-ttu-id="2e8e3-397">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-397">String</span></span>|
|<span data-ttu-id="2e8e3-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-398">COLUMN_TYPE</span></span>|<span data-ttu-id="2e8e3-399">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-399">Int16</span></span>|
|<span data-ttu-id="2e8e3-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-400">DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-401">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-401">Int16</span></span>|
|<span data-ttu-id="2e8e3-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-402">TYPE_NAME</span></span>|<span data-ttu-id="2e8e3-403">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-403">String</span></span>|
|<span data-ttu-id="2e8e3-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-404">PRECISION</span></span>|<span data-ttu-id="2e8e3-405">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-405">Int32</span></span>|
|<span data-ttu-id="2e8e3-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-406">LENGTH</span></span>|<span data-ttu-id="2e8e3-407">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-407">Int32</span></span>|
|<span data-ttu-id="2e8e3-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-408">SCALE</span></span>|<span data-ttu-id="2e8e3-409">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-409">Int16</span></span>|
|<span data-ttu-id="2e8e3-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="2e8e3-410">RADIX</span></span>|<span data-ttu-id="2e8e3-411">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-411">Int16</span></span>|
|<span data-ttu-id="2e8e3-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-412">NULLABLE</span></span>|<span data-ttu-id="2e8e3-413">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-413">Int16</span></span>|
|<span data-ttu-id="2e8e3-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-414">REMARKS</span></span>|<span data-ttu-id="2e8e3-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-415">String</span></span>|
|<span data-ttu-id="2e8e3-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="2e8e3-416">OVERLOAD</span></span>|<span data-ttu-id="2e8e3-417">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-417">Int32</span></span>|
|<span data-ttu-id="2e8e3-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="2e8e3-419">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="2e8e3-420">Microsoft Jet ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="2e8e3-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="2e8e3-421">Der Microsoft Jet ODBC-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="2e8e3-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="2e8e3-422">Tabellen</span><span class="sxs-lookup"><span data-stu-id="2e8e3-422">Tables</span></span>

- <span data-ttu-id="2e8e3-423">Indizes</span><span class="sxs-lookup"><span data-stu-id="2e8e3-423">Indexes</span></span>

- <span data-ttu-id="2e8e3-424">Spalten</span><span class="sxs-lookup"><span data-stu-id="2e8e3-424">Columns</span></span>

- <span data-ttu-id="2e8e3-425">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2e8e3-425">Procedures</span></span>

- <span data-ttu-id="2e8e3-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2e8e3-426">ProcedureColumns</span></span>

- <span data-ttu-id="2e8e3-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2e8e3-427">ProcedureParameters</span></span>

- <span data-ttu-id="2e8e3-428">Ansichten</span><span class="sxs-lookup"><span data-stu-id="2e8e3-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="2e8e3-429">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="2e8e3-429">Tables and Views</span></span>

|<span data-ttu-id="2e8e3-430">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-430">ColumnName</span></span>|<span data-ttu-id="2e8e3-431">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="2e8e3-433">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-433">String</span></span>|
|<span data-ttu-id="2e8e3-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-434">TABLE_OWNER</span></span>|<span data-ttu-id="2e8e3-435">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-435">String</span></span>|
|<span data-ttu-id="2e8e3-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-436">TABLE_NAME</span></span>|<span data-ttu-id="2e8e3-437">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-437">String</span></span>|
|<span data-ttu-id="2e8e3-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-438">TABLE_TYPE</span></span>|<span data-ttu-id="2e8e3-439">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-439">String</span></span>|
|<span data-ttu-id="2e8e3-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-440">REMARKS</span></span>|<span data-ttu-id="2e8e3-441">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="2e8e3-442">Spalten</span><span class="sxs-lookup"><span data-stu-id="2e8e3-442">Columns</span></span>

|<span data-ttu-id="2e8e3-443">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-443">ColumnName</span></span>|<span data-ttu-id="2e8e3-444">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="2e8e3-446">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-446">String</span></span>|
|<span data-ttu-id="2e8e3-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-447">TABLE_OWNER</span></span>|<span data-ttu-id="2e8e3-448">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-448">String</span></span>|
|<span data-ttu-id="2e8e3-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-449">TABLE_NAME</span></span>|<span data-ttu-id="2e8e3-450">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-450">String</span></span>|
|<span data-ttu-id="2e8e3-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-451">COLUMN_NAME</span></span>|<span data-ttu-id="2e8e3-452">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-452">String</span></span>|
|<span data-ttu-id="2e8e3-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-453">DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-454">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-454">Int16</span></span>|
|<span data-ttu-id="2e8e3-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-455">TYPE_NAME</span></span>|<span data-ttu-id="2e8e3-456">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-456">String</span></span>|
|<span data-ttu-id="2e8e3-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-457">PRECISION</span></span>|<span data-ttu-id="2e8e3-458">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-458">Int32</span></span>|
|<span data-ttu-id="2e8e3-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-459">LENGTH</span></span>|<span data-ttu-id="2e8e3-460">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-460">Int32</span></span>|
|<span data-ttu-id="2e8e3-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-461">SCALE</span></span>|<span data-ttu-id="2e8e3-462">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-462">Int16</span></span>|
|<span data-ttu-id="2e8e3-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="2e8e3-463">RADIX</span></span>|<span data-ttu-id="2e8e3-464">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-464">Int16</span></span>|
|<span data-ttu-id="2e8e3-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-465">NULLABLE</span></span>|<span data-ttu-id="2e8e3-466">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-466">Int16</span></span>|
|<span data-ttu-id="2e8e3-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-467">REMARKS</span></span>|<span data-ttu-id="2e8e3-468">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-468">String</span></span>|
|<span data-ttu-id="2e8e3-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="2e8e3-470">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="2e8e3-471">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2e8e3-471">Procedures</span></span>

|<span data-ttu-id="2e8e3-472">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-472">ColumnName</span></span>|<span data-ttu-id="2e8e3-473">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="2e8e3-475">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-475">String</span></span>|
|<span data-ttu-id="2e8e3-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="2e8e3-477">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-477">String</span></span>|
|<span data-ttu-id="2e8e3-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="2e8e3-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-479">String</span></span>|
|<span data-ttu-id="2e8e3-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="2e8e3-481">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-481">Int16</span></span>|
|<span data-ttu-id="2e8e3-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="2e8e3-483">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-483">Int16</span></span>|
|<span data-ttu-id="2e8e3-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="2e8e3-485">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-485">Int16</span></span>|
|<span data-ttu-id="2e8e3-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-486">REMARKS</span></span>|<span data-ttu-id="2e8e3-487">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-487">String</span></span>|
|<span data-ttu-id="2e8e3-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="2e8e3-489">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="2e8e3-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="2e8e3-490">ProcedureColumns</span></span>

|<span data-ttu-id="2e8e3-491">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-491">ColumnName</span></span>|<span data-ttu-id="2e8e3-492">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="2e8e3-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-494">String</span></span>|
|<span data-ttu-id="2e8e3-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e8e3-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="2e8e3-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-496">String</span></span>|
|<span data-ttu-id="2e8e3-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="2e8e3-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-498">String</span></span>|
|<span data-ttu-id="2e8e3-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-499">COLUMN_NAME</span></span>|<span data-ttu-id="2e8e3-500">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-500">String</span></span>|
|<span data-ttu-id="2e8e3-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-501">COLUMN_TYPE</span></span>|<span data-ttu-id="2e8e3-502">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-502">Int16</span></span>|
|<span data-ttu-id="2e8e3-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-503">DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-504">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-504">Int16</span></span>|
|<span data-ttu-id="2e8e3-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-505">TYPE_NAME</span></span>|<span data-ttu-id="2e8e3-506">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-506">String</span></span>|
|<span data-ttu-id="2e8e3-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-507">PRECISION</span></span>|<span data-ttu-id="2e8e3-508">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-508">Int32</span></span>|
|<span data-ttu-id="2e8e3-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-509">LENGTH</span></span>|<span data-ttu-id="2e8e3-510">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-510">Int32</span></span>|
|<span data-ttu-id="2e8e3-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-511">SCALE</span></span>|<span data-ttu-id="2e8e3-512">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-512">Int16</span></span>|
|<span data-ttu-id="2e8e3-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="2e8e3-513">RADIX</span></span>|<span data-ttu-id="2e8e3-514">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-514">Int16</span></span>|
|<span data-ttu-id="2e8e3-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-515">NULLABLE</span></span>|<span data-ttu-id="2e8e3-516">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-516">Int16</span></span>|
|<span data-ttu-id="2e8e3-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-517">REMARKS</span></span>|<span data-ttu-id="2e8e3-518">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-518">String</span></span>|
|<span data-ttu-id="2e8e3-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="2e8e3-519">OVERLOAD</span></span>|<span data-ttu-id="2e8e3-520">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-520">Int32</span></span>|
|<span data-ttu-id="2e8e3-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="2e8e3-522">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="2e8e3-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="2e8e3-523">ProcedureParameters</span></span>

|<span data-ttu-id="2e8e3-524">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="2e8e3-524">ColumnName</span></span>|<span data-ttu-id="2e8e3-525">DataType</span><span class="sxs-lookup"><span data-stu-id="2e8e3-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="2e8e3-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="2e8e3-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="2e8e3-527">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-527">String</span></span>|
|<span data-ttu-id="2e8e3-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="2e8e3-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="2e8e3-529">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-529">String</span></span>|
|<span data-ttu-id="2e8e3-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="2e8e3-531">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-531">String</span></span>|
|<span data-ttu-id="2e8e3-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-532">COLUMN_NAME</span></span>|<span data-ttu-id="2e8e3-533">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-533">String</span></span>|
|<span data-ttu-id="2e8e3-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-534">COLUMN_TYPE</span></span>|<span data-ttu-id="2e8e3-535">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-535">Int16</span></span>|
|<span data-ttu-id="2e8e3-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-536">DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-537">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-537">Int16</span></span>|
|<span data-ttu-id="2e8e3-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="2e8e3-538">TYPE_NAME</span></span>|<span data-ttu-id="2e8e3-539">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-539">String</span></span>|
|<span data-ttu-id="2e8e3-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-540">COLUMN_SIZE</span></span>|<span data-ttu-id="2e8e3-541">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-541">Int32</span></span>|
|<span data-ttu-id="2e8e3-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="2e8e3-543">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-543">Int32</span></span>|
|<span data-ttu-id="2e8e3-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="2e8e3-545">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-545">Int16</span></span>|
|<span data-ttu-id="2e8e3-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="2e8e3-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="2e8e3-547">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-547">Int16</span></span>|
|<span data-ttu-id="2e8e3-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-548">NULLABLE</span></span>|<span data-ttu-id="2e8e3-549">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-549">Int16</span></span>|
|<span data-ttu-id="2e8e3-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="2e8e3-550">REMARKS</span></span>|<span data-ttu-id="2e8e3-551">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-551">String</span></span>|
|<span data-ttu-id="2e8e3-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="2e8e3-552">COLUMN_DEF</span></span>|<span data-ttu-id="2e8e3-553">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-553">String</span></span>|
|<span data-ttu-id="2e8e3-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="2e8e3-555">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-555">Int16</span></span>|
|<span data-ttu-id="2e8e3-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="2e8e3-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="2e8e3-557">Int16</span><span class="sxs-lookup"><span data-stu-id="2e8e3-557">Int16</span></span>|
|<span data-ttu-id="2e8e3-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2e8e3-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="2e8e3-559">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-559">Int32</span></span>|
|<span data-ttu-id="2e8e3-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="2e8e3-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="2e8e3-561">Int32</span><span class="sxs-lookup"><span data-stu-id="2e8e3-561">Int32</span></span>|
|<span data-ttu-id="2e8e3-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2e8e3-562">IS_NULLABLE</span></span>|<span data-ttu-id="2e8e3-563">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2e8e3-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="2e8e3-564">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e8e3-564">See also</span></span>

- [<span data-ttu-id="2e8e3-565">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2e8e3-565">ADO.NET Overview</span></span>](ado-net-overview.md)
