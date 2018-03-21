![Androsia Logo](logo.png)
# Androsia
Androsia is a tool written in Java aimed at analysing Android applications to detect last use of StringBuilder objects. Androsia instruments code to clear memory contents of these objects after their last use so that any sensitive information is destroyed and does not appear in a heap dump. As a result, if an application process gets compromised, the attacker would not be able to extract any sensitive information from a dump.

## Built With

* [Soot](https://sable.github.io/soot/) - The framework used for analyzing and transforming Android applications
* [FlowDroid](https://blogs.uni-paderborn.de/sse/tools/flowdroid/) - Tool used to generate callgraph for Android applications


## Project Resources

We recommend jumping into the quick start guide [quickstart.md](quickstart.md) — you'll have a demo up and running in minutes.

## Authors

* **Samit Anwer** 

## License

Copyright (c) 2017 Samit Anwer

This project is licensed under the Apache License Version 2.0 - see the [LICENSE.md](LICENSE.md) file for details; you may not use this file except in compliance with the License. You may also obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

