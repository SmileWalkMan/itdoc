https://www.npmjs.com/package/carbon-components-react

## >npm install -g create-react-app
## >create-react-app my-new-app　　 （“my-new-app”是你的项目根目录文件夹名称）

## >npm install -S carbon-components carbon-components-react carbon-icons

### Then we need to include carbon-components in index.css:
@import "~carbon-components/css/carbon-components.css";

## 对应的模版里面添加App.js 添加代码
import { Button,Checkbox,Dropdown,MultiSelect } from 'carbon-components-react';


function App() {
  return (
    <div dir="rtl" className="App">
      <Button>Example usage</Button>
    </div>
  );
}
export default App;
