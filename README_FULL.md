# Task Management & Productivity Tracker

A comprehensive task management and productivity tracking application built with **Angular 21**, **TypeScript**, and **RxJS**. This project demonstrates modern Angular architecture with standalone components, reactive programming, and advanced form handling.

## 🎯 Project Features

### Core Functionality
- ✅ **Create Tasks** - Add new tasks with title, description, category, priority, and due date
- ✅ **View Tasks** - Display all tasks in a responsive grid layout
- ✅ **Edit Tasks** - Modify existing task details
- ✅ **Delete Tasks** - Remove tasks with confirmation
- ✅ **Track Status** - Update task status (Pending, In Progress, Completed)
- ✅ **Filter Tasks** - Filter by task status
- ✅ **Task Details** - View complete task information on a dedicated page

### Technical Implementation
- **TypeScript Classes & Interfaces** - Robust type checking with Task, Category, User models
- **Angular Routing** - Clean navigation with route guards and parameters
- **Data Binding** - Two-way binding with `[(ngModel)]` and event binding
- **Directives** - `*ngFor` for loops, `*ngIf` for conditionals, `[ngClass]` and `[ngStyle]` for dynamic styling
- **Reactive Forms** - Template-driven forms with validation
- **RxJS Services** - Observable-based data management with BehaviorSubject
- **Responsive Design** - Mobile-first CSS styling with media queries
- **State Management** - Service-based state with real-time updates

## 📁 Project Structure

```
task-management-app/
├── src/
│   ├── app/
│   │   ├── models/
│   │   │   └── task.model.ts         # Task data models, enums, and classes
│   │   ├── services/
│   │   │   └── task.ts               # Task service with RxJS observables
│   │   ├── components/
│   │   │   ├── navbar/               # Navigation component
│   │   │   ├── task-list/            # Display all tasks with filtering
│   │   │   ├── task-form/            # Create/edit task form
│   │   │   └── task-detail/          # View single task details
│   │   ├── app.ts                    # Root component
│   │   ├── app.routes.ts             # Routing configuration
│   │   ├── app.html                  # Root template
│   │   ├── app.css                   # Root styles
│   │   └── app.config.ts             # App configuration
│   ├── styles.css                    # Global styles
│   ├── main.ts                       # Bootstrap file
│   └── index.html                    # HTML entry point
├── angular.json                      # Angular CLI configuration
├── tsconfig.json                     # TypeScript configuration
└── package.json                      # Dependencies

```

## 🚀 Getting Started

### Prerequisites
- Node.js (v18 or higher)
- Angular CLI (v21.1.1+)
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/SamDesilva-04/Task-Management-Productivity-Tracker.git
   cd task-management-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   ng serve
   # or
   npm start
   ```

4. **Open in browser**
   Navigate to `http://localhost:4200/` in your browser

### Building for Production
```bash
ng build --configuration production
```

The build artifacts will be stored in the `dist/` directory.

## 📦 Data Models

### TaskCategory Enum
```typescript
enum TaskCategory {
  WORK = 'Work',
  PERSONAL = 'Personal',
  SHOPPING = 'Shopping',
  HEALTH = 'Health',
  EDUCATION = 'Education'
}
```

### TaskPriority Enum
```typescript
enum TaskPriority {
  LOW = 'Low',
  MEDIUM = 'Medium',
  HIGH = 'High'
}
```

### TaskStatus Enum
```typescript
enum TaskStatus {
  PENDING = 'Pending',
  IN_PROGRESS = 'In Progress',
  COMPLETED = 'Completed'
}
```

### Task Interface & TaskModel Class
```typescript
interface Task {
  id: string;
  title: string;
  description: string;
  category: TaskCategory;
  priority: TaskPriority;
  status: TaskStatus;
  dueDate: Date;
  createdDate: Date;
  completedDate?: Date;
  assignedTo?: User;
}

class TaskModel implements Task {
  // Methods:
  // - isOverdue(): boolean
  // - markAsCompleted(): void
  // - markAsInProgress(): void
  // - markAsPending(): void
  // - getProgressPercentage(): number
}
```

## 🛠️ Available Services

### TaskService

**Methods:**
- `getTasks()` - Returns Observable of all tasks
- `getTaskById(id)` - Get specific task by ID
- `addTask(task)` - Add new task to the list
- `updateTask(task)` - Update existing task
- `deleteTask(id)` - Delete task by ID
- `getTasksByCategory(category)` - Filter tasks by category
- `getTasksByPriority(priority)` - Filter tasks by priority
- `getTasksByStatus(status)` - Filter tasks by status
- `getCompletedTasks()` - Get all completed tasks
- `getPendingTasks()` - Get all pending tasks
- `getProgressStats()` - Get productivity statistics

## 🎨 Component Architecture

### Navbar Component
- Navigation menu with links to Dashboard and Add Task
- Sticky positioning for easy access
- Responsive mobile menu

### Task List Component
- Display tasks in a responsive grid
- Filter buttons by status (All, Pending, In Progress, Completed)
- Task cards with:
  - Title, description, and category
  - Priority badge
  - Due date display
  - Status indicator
  - Quick action buttons
- Quick status toggle
- Edit and delete functionality

### Task Form Component
- Create new tasks
- Edit existing tasks
- Form fields:
  - Title (required)
  - Description (required)
  - Category (dropdown)
  - Priority (dropdown)
  - Due Date (date picker)
- Form validation
- Reset and cancel options

### Task Detail Component
- View complete task information
- Edit and delete buttons
- Status transition buttons
- Go back to list

## 🎨 Styling Features

- **Color Scheme:**
  - Primary: #3498db (Blue)
  - Success: #27ae60 (Green)
  - Danger: #e74c3c (Red)
  - Warning: #f39c12 (Orange)
  - Info: #17a2b8 (Teal)

- **Responsive Design:**
  - Mobile-first approach
  - Breakpoint at 768px
  - Flexible grid layouts
  - Touch-friendly buttons

- **Visual Feedback:**
  - Hover effects on buttons and links
  - Status-based color coding
  - Priority indicators
  - Loading states

## 🔄 Data Flow

1. **User Interaction** → Component Event Handler
2. **Service Method** → Update State (BehaviorSubject)
3. **Observable Stream** → Components Subscribe
4. **Template Updates** → Change Detection

## 📱 Responsive Breakpoints

- **Mobile** (< 768px): Single column layout, stacked buttons
- **Tablet** (768px - 1024px): 2-column grid
- **Desktop** (> 1024px): 3-column grid with full features

## 🧪 Angular Features Used

✅ **Standalone Components** - Self-contained component architecture
✅ **Routing Module** - Client-side navigation with RouterLink
✅ **Template Directives** - *ngFor, *ngIf, [ngClass], [ngStyle]
✅ **Two-Way Binding** - [(ngModel)] for form inputs
✅ **Event Binding** - (click), (ngSubmit) for user interactions
✅ **Property Binding** - [property] for dynamic values
✅ **Services** - Dependency injection with @Injectable()
✅ **RxJS Observables** - Reactive data streams with BehaviorSubject
✅ **Change Detection** - OnPush strategy optimization
✅ **Lifecycle Hooks** - OnInit, OnDestroy implementation

## 📝 Usage Examples

### Create a Task
```typescript
const newTask = new TaskModel(
  'Complete Angular Project',
  'Build a task management app',
  TaskCategory.WORK,
  TaskPriority.HIGH,
  new Date(2026, 1, 28)
);
this.taskService.addTask(newTask);
```

### Update Task Status
```typescript
task.markAsCompleted();
this.taskService.updateTask(task);
```

### Filter Tasks
```typescript
const workTasks = this.taskService.getTasksByCategory(TaskCategory.WORK);
const highPriority = this.taskService.getTasksByPriority(TaskPriority.HIGH);
```

## 🔐 Form Validation

- Required field validation for title and description
- Date picker for due dates
- Category and priority dropdowns for consistency
- Confirmation dialogs before deletion

## 🚀 Performance Optimizations

- RxJS observables for efficient data streaming
- Lazy loading routes
- Standalone components reduce bundle size
- Change detection strategy optimization
- Responsive images and lazy loading

## 📚 Learning Objectives Met

✅ Angular CLI project setup
✅ TypeScript interfaces and classes
✅ Component architecture and composition
✅ Routing and navigation
✅ Services and dependency injection
✅ RxJS observables and operators
✅ Template directives and data binding
✅ Form handling and validation
✅ CSS styling and responsive design
✅ Git version control with commits

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements.

## 📄 License

This project is open source and available under the MIT License.

## 👨‍💻 Author

**Sam Desilva**
- GitHub: [@SamDesilva-04](https://github.com/SamDesilva-04)

## 🔗 Links

- [Angular Documentation](https://angular.dev)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [RxJS Documentation](https://rxjs.dev)

---

**Created with ❤️ for Learning Angular and TypeScript**
