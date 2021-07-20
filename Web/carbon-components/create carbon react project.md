https://www.npmjs.com/package/carbon-components-react<br>
<br>
## >npm install -g create-react-app<br>
## >create-react-app my-new-app　　 （“my-new-app”是你的项目根目录文件夹名称）<br>
<br>
## >npm install -S carbon-components carbon-components-react carbon-icons<br>
<br>
### Then we need to include carbon-components in index.css:<br>
@import "~carbon-components/css/carbon-components.css";<br>
<br>
## 对应的模版里面添加App.js 添加代码<br>
import { Button,Checkbox,Dropdown,MultiSelect } from 'carbon-components-react';<br>
<br>
<br>
function App() {<br>
return (<br>
<div dir="rtl" className="App"><br>
<Button>Example usage</Button><br>
</div><br>
);<br>
}<br>
export default App;<br>
