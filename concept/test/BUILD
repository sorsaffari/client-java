#
# GRAKN.AI - THE KNOWLEDGE GRAPH
# Copyright (C) 2018 Grakn Labs Ltd
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU Affero General Public License as
# published by the Free Software Foundation, either version 3 of the
# License, or (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU Affero General Public License for more details.
#
# You should have received a copy of the GNU Affero General Public License
# along with this program.  If not, see <https://www.gnu.org/licenses/>.
#

package(default_visibility = ["//visibility:__pkg__"])

load("//dependencies/tools/checkstyle:checkstyle.bzl", "checkstyle_test")

java_test(
    name = "remote-concept-it",
    srcs = ["RemoteConceptIT.java"],
    test_class = "grakn.client.concept.test.RemoteConceptIT",
    deps = [
        # Grakn Core dependencies
        "//:client-java",
        "@graknlabs_grakn_core//concept:concept",
        "@graknlabs_grakn_core//server:server", # NEEDS TO GO
        "@graknlabs_grakn_core//test-integration/rule:grakn-test-server",

        # Grakn Labs dependencies
        "@graknlabs_graql//java:graql",

        # Maven External dependencies
        "//dependencies/maven/artifacts/org/hamcrest:hamcrest-library",
        "//dependencies/maven/artifacts/org/slf4j:slf4j-api",
    ],
    size = "large",
    classpath_resources = [
        "@graknlabs_grakn_core//test-integration/resources:logback-test",
        "@graknlabs_grakn_core//test-integration/resources:cassandra-embedded",
        "@graknlabs_grakn_core//server:conf/grakn.properties"
    ]
)


checkstyle_test(
    name = "checkstyle",
    targets = [":remote-concept-it"],
)
