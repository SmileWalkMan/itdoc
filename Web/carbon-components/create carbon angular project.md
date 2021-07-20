## >ng new <projectname><br>
## >npm i --save carbon-components-angular carbon-components @carbon/icons-angular<br>
<br>
### Then we need to include carbon-components in src/styles.scss:<br>
<br>
@import "~carbon-components/scss/globals/scss/styles.scss";<br>
<br>
## app.module.ts<br>
import { AccordionModule, BreadcrumbModule, ButtonModule, } from 'carbon-components-angular';<br>
<br>
@NgModule({<br>
declarations: [<br>
AppComponent<br>
],<br>
imports: [<br>
BrowserModule,<br>
AppRoutingModule,ButtonModule,<br>
],<br>
providers: [],<br>
bootstrap: [AppComponent]<br>
})<br>
<br>
##<br>
1. html直接添加：<button ibmButton="primary" size="normal">Button2</button><br>
<br>
2. ts添加属性<br>
export class AppComponent {<br>
title = 'bidi-rtlcss';<br>
ibmButton: string;<br>
size: string;<br>
ngOnInit(): void {<br>
this.ibmButton = "primary";<br>
this.size = "normal";<br>
}<br>
}<br>
html直接添加：<br>
<button [ibmButton]="ibmButton" [size]="size">Button</button><br>
